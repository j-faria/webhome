---
layout: post
lang: en
ref: blogpost
comments: true
title:  SWEET-Cat and exoplanet.eu from Python
author: joao
---



Two more Python packages, this time to access the 
[SWEET-Cat](https://www.astro.up.pt/resources/sweet-cat/) and 
[exoplanet.eu](http://exoplanet.eu/) databases.  
<!--  -->
Both packages are quite simple, easy to install from PyPI, and come without any dependencies.
<!-- They are alternatives to other methods  -->

 	
**SWEET-Cat** is a catalogue of stellar parameters for stars with planets.
It compiles sets of atmospheric parameters previously published in the literature 
(Teff, logg, and [Fe/H]) and, whenever possible, 
derived using the same uniform methodology 
(see [Santos et al. 2004](http://adsabs.harvard.edu/abs/2004A%26A...415.1153S); 
     [Sousa et al. 2008](http://adsabs.harvard.edu/abs/2008A%26A...487..373S)).
The catalogue is described in [Santos et al. 2013](http://www.astro.up.pt/investigacao/index.php?WID=233&CID=1&Lang=uk&ID=754). 


**exoplanet.eu** is an online database for extrasolar planet candidates, 
which is updated regularly (daily) as new planet detections become available. 
It contains a number of parameters for each exoplanet,
including orbital parameters and derived quantities, 
as well as some metadata about the discovery.


The [pySWEETCat](https://pypi.org/project/pySWEETCat/) and [pyExoplaneteu](https://pypi.org/project/pyExoplaneteu/) packages
allow for a Python-only, no-frills interface to the two catalogues.
They can be easily installed with 

```
pip install pySWEETCat
pip install pyExoplaneteu
```

To use them from within Python just run

```python
import pysweetcat
import pyexoplaneteu
```

In a deliberate quest for simplicity, the two packages provide only one function,
called `get_data()`, which downloads the data from the online archive and returns it in a dictionary.


```python
dataSC = pysweetcat.get_data()
dataEU = pyexoplaneteu.get_data()
```

This function will start by checking if you downloaded the data before.
If not, or if the data is too old (more than 5 days old), it will download it again.


The two outputs, `dataSC` and `dataEU` are (almost) Python dictionaries,
with each column of the catalogues as keys. 
They are _almost_ dictionaries because they both have a few 
of extra methods and properties which make working with the data even simpler.
For example

```python
>>> dataSC.size
2693
>>> dataEU.size
3869
```

returns the number of values in each column.
That is, the number of stars with parameters in SWEET-Cat, and the number of exoplanets in exoplanet.eu.

The `columns()` method will print (not return!) the available columns.


```python
>>> dataSC.columns()
['name', 'HD', 'ra', 'dec', 'vmag', 'σ_vmag', 'π', 'σ_π', 'source_π', 'teff',
 'σ_teff', 'logg', 'σ_logg', 'LC_logg', 'σ_LC_logg', 'vt', 'σ_vt', 'feh',
 'σ_feh', 'mass', 'σ_mass', 'reference', 'homogeneity', 'last_update',
 'comments']


>>> dataEU.columns()
['name', 'planet_status', 'mass', 'mass_error_min', 'mass_error_max',
 'mass_sini', 'mass_sini_error_min', 'mass_sini_error_max', 'radius',
 'radius_error_min', 'radius_error_max', 'orbital_period'
  ...
```


The columns can be accessed as in a normal dictionary, with

```python
>>> dataSC['vmag']  # the star's magnitude
>>> dataSC['teff']  # the star's effective temperature

>>> dataEU['name']  # the name of the planet
>>> dataEU['mass']  # the mass of the planet
>>> dataEU['star_radius']  # the radius of the host star
```


Also, to drop all the NaN values in a column (for some columns there will be quite a few),
we can append `_nonan` to the name of any column

```python
>>> dataEU['mass_nonan']

# import numpy as np
>>> np.isnan(dataEU['mass']).any()         # True
>>> np.isnan(dataEU['mass_nonan']).any()   # False
```

which allows us to more easily do histograms of the values.


Finally, it is worth mentioning the `.to_numpy(inplace=True)` method,
which converts all the columns (which are lists) to numpy arrays, either in place or not.
This is the only function in both pySWEETCat and pyExoplaneteu that requires numpy.








## wrap up

Two very simple Python packages to access data from SWEET-Cat and exoplanet.eu.  
Let me know in the comments if you find them useful.
<br>
<br>


