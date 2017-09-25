---
layout: post
comments: true
title:  Truncated Distributions
author: joao
---

In a Bayesian model, each parameter needs a prior distribution.
To set these priors, we sometimes want to use standard probability distributions
but constrained to some interval $$[a,b]$$ inside their support.
How to do this?


## tl:dr

Check out [this paper](http://dx.doi.org/10.18637/jss.v016.c02),
eqs. (1-6).

## Formulas

Suppose we have a continuous distribution with probability density function (pdf) and cumulative distribution function (cdf) specified by $$g(·)$$ and $$G(·)$$, respectively.

Let $$X$$ be the random variable representing the truncated version 
of this distribution over the interval $$[a, b]$$, 
where $$-\infty < a < b < \infty$$.
The pdf, cdf and quantile function of $$X$$ are given by

$$
{\rm pdf:}\qquad f_X(x) =
\begin{cases}
\frac{g(x)}{G(b) - G(a)}  & \text{if $a \leq x \leq b$} \\[1ex]
0                         & \text{otherwise}
\end{cases}
$$


$$
{\rm cdf:}\qquad F_X(x) = 
\frac{G({\rm max}({\rm min}(x, b), a)) − G(a)}{G(b) − G(a)}
$$

$$
{\rm quantile:}\qquad F^{-1}_X(p) = 
G^{-1} (G(a) + p (G(b) − G(a))) 
$$


Note one important thing: the support of the truncated distribution
is the same as that of the original distribution.
But the pdf of the truncated distribution is $$0$$ outside the interval $$[a,b]$$.

## Example

As an example, consider the 
[Rayleigh distribution](https://en.wikipedia.org/wiki/Rayleigh_distribution).  
Because this distribution has analytical forms for the pdf and cdf,
it can be a good candidate for a prior
for the eccentricity of an exoplanet orbit, for example.
But the support of the Rayleigh distribution is the interval $$[0,\infty)$$,
and the eccentricity $$e$$ is only defined between 0 and 1 (for elliptical orbits).
So we consider the truncated (only from above) Rayleigh distribution.

We have

$$
g(e|\sigma) = \frac{e}{\sigma^2} \exp\left[-\frac{e^2}{2\sigma^2}\right] ,
$$

$$
G(e|\sigma) = 1 - \exp\left[-\frac{e^2}{2\sigma^2}\right] ,
$$

and 

$$
G^{-1}(p|\sigma) = \sigma \sqrt{-2\ln(1-p)}
$$

Therefore, for the truncated distribution

$$
f_X(e) =
\begin{cases}
\frac{g(e|\sigma)}
     {G(1|\sigma) }  & \text{if $0 \leq e \lt 1$} \\[1ex]
0                         & \text{otherwise}
\end{cases}
$$

$$
F_X(e) = 
\frac{G(e|\sigma)}
     {G(1|\sigma)}
$$

$$
F^{-1}_X(p) = 
G^{-1} \left( \, p \, G(1|\sigma) \,\right)
$$



## Scipy implementation

Scipy already has a number of probability distributions implemented.
I mean, seriously, that's a lot of distributions!!
But only two truncated distributions, the `truncnorm` and `truncexpon`,
corresponding to the truncated Normal distribution
and to the truncated (from above only) Exponential distribution.
Using the formulas above, we can implement a general `truncated` class,
which should work for all the other distributions:

{% highlight python %}
import numpy as np
from scipy import stats

class truncated(stats.rv_continuous):
    def __init__(self, original, a=-np.inf, b=np.inf, *args, **kwargs):
        assert isinstance(original, stats.rv_continuous)
        assert b > a, \
            'upper limit `b` cannot be less than or equal to lower limit `a`'
        super(truncated, self).__init__()

        self.original = original(*args, **kwargs)
        self.original_name = original.name
        self.a, self.b = a, b
        self.g, self.G = self.original.pdf, self.original.cdf
        self.factor = self.G(b) - self.G(a)

    def __call__(self):
        raise NotImplementedError(
            'frozen distributions are not implemented yet...'
            )

    def __repr__(self):
        return 'scipy distribution `%s` truncated to (%.2f, %.2f)' % \
               (self.original_name, self.a, self.b)

    def _pdf(self, x):
        return self.g(x) / self.factor

    def _cdf(self, x):
        d = self.G(np.maximum(np.minimum(x, self.b), self.a)) - self.G(self.a)
        return d / self.factor

    def _ppf(self, q):
        Gm1 = self.original.ppf
        return Gm1(self.G(self.a) + q*self.factor)
{% endhighlight %}


which we would use like

{% highlight python %}
dist = truncated(stats.norm, a=-2, b=2)
{% endhighlight %}

or, for the Rayleigh example above (choosing a scale parameter of $$0.2$$)

{% highlight python %}
dist = truncated(stats.rayleigh, scale=0.2, a=-2, b=2)
{% endhighlight %}


In order to test our implementation, we can compare with `truncnorm` and `truncexpon`.

{% highlight python %}
x = np.linspace(0, 10, 1e5)
assert np.allclose(stats.truncexpon(b=3).pdf(x), 
                   truncated(stats.expon, b=3).pdf(x))

assert np.allclose(stats.truncnorm(a=-1, b=2).cdf(x), 
                   truncated(stats.norm, a=-1, b=2).cdf(x))

p = np.linspace(0, 1)
assert np.allclose(stats.truncnorm(a=-10, b=4).ppf(p), 
                   truncated(stats.norm, a=-10, b=4).ppf(p))
{% endhighlight %}


Because we inherited from `stats.rv_continuous`, 
we automagically have access to other methods as well, besides the ones we implemented.
The following code generates $$100$$ samples from a truncated Cauchy distribution:

{% highlight python %}
truncated(stats.cauchy, a=-3, b=3, loc=1).rvs(size=100)
{% endhighlight %}


## wrap up


Truncating probability distributions to a certain interval inside their support
can sometimes be very useful.
The formulas above describe the pdf, cdf and inverse cdf functions for any truncated distribution,
and the Python implementation complements the distributions already available in Scipy.

Let me know in the comments if this is helpful, wrong or super-duper cool.





