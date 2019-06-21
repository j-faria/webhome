---
layout: post
lang: en
ref: blogpost
comments: true
title: Nightly bin RVs
author: joao
excerpt: A handy function to nightly bin radial-velocity observations.
---

One of the most common operations performed on time series of radial velocities
is to _bin_ a number of measurements performed on the same night.
In a [previous post]({{site.baseurl}}/blog/binning), I briefly talked about
scipy's `binned_statistic` function, which can be used to bin data.
But it turns out this function is missing one important feature
which is necessary for the specific RV use-case.

In this post, I will present a modification of `binned_statistic`
which allows for the use of measurement uncertainties as weights
during the binning calculation. 
This modified function will then be applied to RV time series.

First, some brief words of motivation.  
The _reason_ why we want to bin is not the most important[^1].
On a given night, we might have obtained shorter exposures 
of a very bright star in order not to saturate our detector,
and finally want to combine the measurements. 
Or we might be trying to average out stellar oscillations
by combining two observations from the same night.
Whatever the reason, each RV measurement comes with an associated uncertainty,
which we might want to use during the binning.
This will allow us to _weigh_ each RV point individually.
In addition, we are also interested in combining the times of the observations,
as well as the uncertainty measures themselves.


## changes to `binned_satistic`

The implementation of this function in scipy can be found 
[here](https://github.com/scipy/scipy/blob/master/scipy/stats/_binned_statistic.py).
After checking some of the arguments, the `binned_statistic` function
calls `binned_statistic_dd` and builds a custom namedtuple 
with the result[^2] before returning.

We need to re-write both `binned_statistic` and `binned_statistic_dd`,
if we want to include an extra parameter "`weights`".
In the following, I will leave out the modifications to the doc strings
as they (the doc strings) are quite lengthy.
At the end of the post, you can find 
the full implementation including these changes.


For our script to be self-contained, we first need some imports

```python
import numpy as np
from scipy._lib.six import callable, xrange
from scipy._lib._numpy_compat import suppress_warnings
```

Now, the modified `binned_statistic` function:

```python
def binned_statistic(x, values, statistic='mean', bins=10, 
                     range=None, weights=None):
  try:
    N = len(bins)
  except TypeError:
    N = 1

  if N != 1:
    bins = [np.asarray(bins, float)]

  if range is not None:
    if len(range) == 2:
      range = [range]

  medians, edges, binnumbers = binned_statistic_dd(
    [x], values, statistic, bins, range, weights)

  return medians, edges[0], binnumbers
```

Yes, that's anticlimactic. 
The only modifications to the original function are the inclusion of
`weights` in the arguments and in the call to `binned_statistic_dd`.

So, it's `binned_statistic_dd` which is doing all the work.
But, even there, not much really changes:

```python
def binned_statistic_dd(sample, values, statistic='mean', bins=10, 
                        range=None, weights=None, 
                        expand_binnumbers=False):
    
  ## ...
  ## nothing changes
  ## ...

  values = np.atleast_2d(values)
  if weights is not None:
    weights = np.atleast_2d(weights)

  ## ...
  ## nothing changes
  ## ...

  elif callable(statistic):
    with np.errstate(invalid='ignore'), suppress_warnings() as sup:
      sup.filter(RuntimeWarning)
      try:
        if weights is None:
          null = statistic([])
        else:
          null = statistic([], weights=[])
      except:
        null = np.nan
      result.fill(null)
      for i in np.unique(binnumbers):
        for vv in xrange(Vdim):
          which = binnumbers == i
          if weights is None:
            result[vv, i] = statistic(values[vv, which])
          else:
            result[vv, i] = statistic(values[vv, which],
                                      weights=weights[vv, which])

  ## ...
  ## nothing changes
  ## ...
  
  return result, edges, binnumbers
```

Besides adding `weights` as an argument 
and making sure it has the correct shape,
we only change the code for the cases when `statistic` is a callable.
In these cases, we will need to provide a function `f(values, weights)`
that will do the actual binning.

These small modifications already make `binned_statistic` 
able to calculate a weighted average within the bins,
by using the appropriate statistic[^3]:


```python
result = binned_statistic(x, values, statistic=np.average, 
                          weights=error_values):
```


## radial velocities

Now let's go into our application to radial velocity time series.  
The typical dataset will have times, radial velocities, and uncertainties

```python
time, rv, err = data
```

and we want a function to nightly bin the three arrays.
The first step will be to define the bins, 
based on the integer part of the array of times:

```python
intt = time.astype(int)
_, indices = np.unique(intt, return_index=True)
```

We will have to be a bit careful to create one extra bin
so that the last time is included.
If the last time is "alone" and doesn't actually need to be binned,
we need to make sure the bin edge is not exactly equal to `time[-1]`

```python
if indices[-1] == time.size - 1:
    bins = np.r_[time[indices], time[-1] + 1e-10]
else:
    bins = np.r_[time[indices], time[-1]]
```


That was the hard part.
Now, we define a function to calculate a variance-weighted average,
which we will use as the default for the times and radial velocities
when the uncertainties are provided.

```python
# weighted mean
wmean = lambda a, e: np.average(a, weights=1/e**2)
```

We use the new `binned_statistic` to bin the radial velocities
using the weighted mean

```python
stat = wmean
brv = binned_statistic(time, rv, statistic=stat, bins=bins,
                       weights=err)
```

and the times, also using the weighted mean

```python
tstat = wmean
btime = binned_statistic(time, time, statistic=tstat, bins=bins,
                         weights=err)
```

For binning the uncertainties, we have a few choices.
I think the most statistically-justified option 
is to add the uncertainties quadratically, like this

```python
add_quadratically = lambda a: np.sqrt(np.add.reduce(a**2))
mean_quadratically = lambda a: add_quadratically(a) / a.size
estat = mean_quadratically
berr = binned_statistic(time, err, statistic=estat, bins=bins)
```

Note that `add_quadratically` and `mean_quadratically` 
are only separated for clarity, and they could very easily be merged.
If we assume each radial-velocity measurement to be a Gaussian random variable
with variance given by the square of the associated uncertainty,
then this is the correct approach when binning.
But sometimes you might be interested in performing another operation
on the uncertainties, such as a simple average:

```python
berr = binned_statistic(time, err, statistic='mean', bins=bins)
```

By the end, the binned times, radial velocities and uncertainties
will be the first values of `btime`, `brv`, and `berr`.
In summary, joining everything in a function:

```python
def binRV(time, rv, err, stat='wmean', tstat='wmean', estat='addquad'):
    """ Bin a dataset of radial-velocity observations.

    Parameters
    ----------
    time : array
        The array of times where the radial velocity is measured. 
        This function does nightly binning, based on the integer part 
        of this array.
    rv : array
        The radial-velocity values.
    err : array (optional)
        The uncertainty on the radial-velocity values.
    stat : string or callable (optional)
        The statistic to compute for the radial velocities. By default, 
        this is the weighted mean ('wmean') in which case the routine 
        does inverse variance averaging, using 1/`err`**2 as weights. 
    tstat : string or callable (optional)
        The statistic to compute for the times. The default is the same 
        as for the radial velocities.
    estat : string or callable (optional)
        The statistic to compute for the errors. The default is to add
        them quadratically and divide by the number in each bin.

    Notes
    -----
    Arguably, the most justified way to perform binning is to use the 
    defaults. This will lead to a weighted average of the times and the
    radial velocities, and quadratically added errors.

    Other options for `stat`, `tstat`, and `estat` are:
    'mean', 'median', 'count', 'sum', 'min', 'max', in addition to 
    any callable of the form `f(array, weights)`.
    """

    intt = time.astype(int)
    _, indices = np.unique(intt, return_index=True)

    if indices[-1] == time.size - 1:
        bins = np.r_[time[indices], time[-1] + 1e-10]
    else:
        bins = np.r_[time[indices], time[-1]]

    wmean = lambda a, e: np.average(a, weights=1 / e**2)

    if stat == 'wmean':
        stat = wmean

    brv = binned_statistic(time, rv, statistic=stat, bins=bins, 
                           weights=err)

    if tstat == 'wmean':
        tstat = wmean

    btime = binned_statistic(time, time, statistic=tstat, bins=bins,
                             weights=err)

    if estat == 'addquad':
        add_quadratically = lambda a: np.sqrt(np.add.reduce(a**2))
        mean_quadratically = lambda a: add_quadratically(a) / a.size
        estat = mean_quadratically
        berr = binned_statistic(time, err, statistic=estat, bins=bins)
    else:
        berr = binned_statistic(time, err, statistic=estat, bins=bins,
                                weights=err)

    return btime[0], brv[0], berr[0]
```


## wrap up

And there we have it, a relatively simple function to nightly bin
a dataset of radial velocities.
I have not done any serious performance tests,[^4]
but I expect this function to be fast enough for most of your needs.
Let me know in the comments if there's something missing.


### scripts

The full script can be found [here](https://gist.github.com/j-faria/32c752dc90dae928a1641b59a60f4eaa).
<!-- <script src="https://gist.github.com/j-faria/32c752dc90dae928a1641b59a60f4eaa.js"></script> -->

### notes


[^1]: Actually, it is. Think before you bin!
[^2]: No idea why.
[^3]: Maybe that alone would be worth a pull request 🤔
[^4]: Apart from timing `np.sum` vs `np.add.reduce`


