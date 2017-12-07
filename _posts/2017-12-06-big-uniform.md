---
layout: post
comments: true
title: A big uniform
author: joao
---

This post was inspired by something Brendon Brewer said
on the [ESAC Data Analysis & Statistics Workshop](https://www.cosmos.esa.int/web/esac-stats-workshop-2017), last week.


Suppose there's a parameter $$x$$ in your Bayesian model,
which you presumably know nothing about.
In order to be "uninformative" and "objective" you might be tempted to assign it
a uniform prior within a big range, say (for illustrative purposes)

$$ x \sim U(0, 10^{20}) $$ 

or, in Python,

```python
from scipy import stats
dist = stats.uniform(0, 1e20)
```

You might be surprised to know that this prior is anything but uninformative.
Let's see why.

First, we estimate the probability that $$x$$ is larger than a given value.
We use the Scipy distribution `sf` method, which calculates
the _survival function_ or 1-cdf.

```python
dist.cdf(0.)    # --> 0.0
dist.sf(0.)     # --> 1.0

dist.cdf(1e20)  # --> 1.0
dist.sf(1e20)   # --> 0.0

dist.sf(1e18)   # --> 0.98999999999999999
```

So, we know nothing about $$x$$, but assign $$99\%$$ probability 
that it is larger than $$10^{18}$$...  
And, to double precision, the probability that x is larger than $$5000$$ is actually 1.

```python
dist.sf(5e3)    # --> 1.0
```


Related to this, we might wonder what happens if in our model there is another parameter
$$y$$ which is given by the sum of 5 x's like so

$$ y = x_1 + x_2 + x_3 + x_4 + x_5 $$

with $$ x_i \sim U(0, 10^{20}) $$.
What are we assuming about $$y$$ by setting these priors of the $$x_i$$.
Presumably, not much, since we are being "uninformative" about the $$x_i$$.


```python
import matplotlib.pyplot as plt

samples = [dist.rvs(5).sum() for _ in range(1000)]
plt.hist(samples); plt.xlabel('y')

## fit a Gaussian distribution
print stats.norm.fit(samples) # --> (2.467719e+20, 6.331523e+19)
```

![sum_big_uniforms](assets/sum_big_uniforms.png)

As it turns out, $$y$$ is very constrained just from the priors for the $$x_i$$!  
(that distribution is not actually a Gaussian, 
see the [Irwin–Hall distribution](https://en.wikipedia.org/wiki/Irwin–Hall_distribution))


## wrap up

Be careful with "uninformative" priors!  
Note that situations similar to the one I describe here (even if more moderate)
can easily go unnoticed in larger models with many parameters.

<br>
Let me know in the comments if this is helpful, wrong or super-duper cool.

