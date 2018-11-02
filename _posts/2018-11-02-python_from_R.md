---
layout: post
comments: true
title:  Calling Python from R
author: joao
excerpt: A simple post to showcase the "reticulate" package.
---


I've recently been trying to use [R](https://www.r-project.org/) 
to leverage some of the excellent packages developed in this language.
But my expertise is in Python and I wanted to avoid having to learn a new language,
at least in an early phase when I'm just trying things out.

Enter [**reticulate**](https://rstudio.github.io/reticulate/),
a package which can connect Python and R.

Assuming your R environment is set up properly
(I found it quite easy to use anaconda to manage R, by just creating a new environment),
all you need to do is install the package

```r
install.packages("reticulate")
```

and, after you load it

```r
library(reticulate)
```

Python will be readily available:


```r
np = import("numpy")

a = np$linspace(0, 1, 100)
a
  [1] 0,00000000 0,01010101 ...
  ....
 [97] 0,96969697 0,97979798 0,98989899 1,00000000

# could be done in standard R with 
a = seq(from=0, to=1, length.out=100)


stats = import("scipy.stats")
stats$norm(0,1)$pdf(0)
[1] 0,3989423

# could be done in standard R with 
dnorm(0)
[1] 0,3989423
```


**reticulate** works by embedding a Python session within the R session,
allowing for this incredibly simple interoperability.
Behind the scenes, all (Python/R) data types are being automatically converted 
to their equivalent (R/Python) types. 
When values are returned from Python to R they are converted back to R types. 
Everything seems to *just work*!

I did notice a performance hit: calling the Python functions was significantly
slower than calling the R functions (though I only tested very few cases). 
This is to be expected, but I don't think it is a show stopper at all.
At the level that I intend to use this package,
the time I spend writing code is much more important than the time the code takes to run.


## wrap up
A powerful but simple way to call Python from within R. Give a try!

<br>
btw: this is [#AcaDoWriMo](https://blogs.agu.org/geoedtrek/2014/11/02/need-motivation-write-join-acadowrimo-november/)!

<!-- <br> -->


