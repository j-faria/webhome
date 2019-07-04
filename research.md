---
layout: page
title: "Research"
lang: en
ref: research
permalink: research
group: "navigation"
navigation_title: Research
navigation_order: 3
---

_I'm still writing a few more words about my research, come back in a few days._


### What I do for a living

I search for exoplanets. Planets around other stars.  
The ultimate goal is to find an Earth-like planet orbiting a solar-like star.  
But that's not so easy. 
Low-mass planets (like the Earth) impart tiny effects on their host stars,
in particular changing their _radial velocity_ (RV) or their brightness. 
This is the basis of the RV 
(not [that](https://www.amazon.com/RV-Method-Improvisational-Scene-Building/dp/0986071447)) 
and transit (not [that](https://transitmethod.bandcamp.com/)) methods for planet detection.


{% include image.html 
    url="https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif"
    description="The idea behind the RV method. Credit: NASA JPL"
%}



<!-- <img src="https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif" alt="rvmethod" width="80%"/> -->

<!-- ![](https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif) -->
<!-- *The idea behind the RV method. Credit: NASA JPL* -->

The whole problem boils down to finding periodic signals of very low amplitude

...

During my PhD, I was in charge of a radial-velocity survey of metal-poor stars, 
with the goal of estimating the occurrence rate of low-mass planets in the low metallicity regime.
I found a planet occurrence rate smaller than that of solar-metallicity stars,
which means that the famous giant planet -- metallicity correlation
also extends to the population of low-mass planets.



### Software

{% assign repos = site.github.public_repositories | where:"fork",false %}
{% assign disprepos = "kima,bgls,SAM,keplerian" | split: "," %}
{% assign numRepos = site.github.public_repositories | size %}
{% assign numMembers = site.github.organization_members | size %}

I enjoy writing code and developing software for science.  
Most of my projects can be found on Github.
Here are some important ones:


{% for repo in repos %}
{% if disprepos contains repo.name %}
**[{{ repo.name }}]({{repo.html_url}})** - {{repo.description}}  
{% endif%}
{% endfor %}

Over at the [blog]({{site.baseurl}}/blog), I've talked about a number
of other small codes.


<!-- [link]({{ repo.html_url }})
{{ repo.license.name }} -->
<!-- | | [![GitHub: repository](https://img.shields.io/badge/GitHub-repo-orange.svg)]({{ repo.html_url }}) -->
<!-- [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) -->
  <!-- {%- if repo.name == "keplerian" %}
    [![PyPI](https://img.shields.io/pypi/v/keplerian.svg)](https://pypi.python.org/pypi/keplerian)
    [![Travis](https://img.shields.io/travis/j-faria/keplerian.svg)](https://travis-ci.org/j-faria/keplerian)
    [![Docs](https://readthedocs.org/projects/keplerian/badge/?version=latest)](https://keplerian.readthedocs.i
o/en/latest/?badge=latest)
  {%- endif %}
  {%- if repo.name == "kima" %}
    [![Build Status](https://travis-ci.org/j-faria/kima.svg?branch=master)](https://travis-ci.org/j-faria/kima)
    [![status](https://joss.theoj.org/papers/b396d6f8c5566bb67844f05bda0cbc8a/status.svg)](https://joss.theoj.o
rg/papers/b396d6f8c5566bb67844f05bda0cbc8a)
  {%- endif %} -->
<!-- {{ repo | strip_newlines }} -->
<!--  -->



<!-- ADS custom format:
 - [%T](%u)  \n%10.1G  \n%Q \n\n 
 <li><a href="%u">%T</a> <br> %3.1G<br> %Q </li> \n

 would be useful to write a script...
-->


### Publications

I am co-author of {{ site.npapers }} refereed research papers.
Here's a list:

<div class="post-pubs">
<ul>

<!-- python get_papers.py, then paste here -->

<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019A&A...621A.110B/abstract"> 
 The GAPS Programme with HARPS-N at TNG. XVIII. Two new giant planets around the metal-poor stars HD 220197 and HD 233832 </a> <br>  Barbato et al. 2019,  A&amp;A, 621, A110 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...619A.150O/abstract"> 
 Activity induced variation in spin-orbit angles as derived from Rossiter-McLaughlin measurements </a> <br>  Oshagh et al. 2018,  A&amp;A, 619, A150 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...620A..58S/abstract"> 
 SWEET-Cat updated. New homogenous spectroscopic parameters </a> <br>  Sousa et al. 2018,  A&amp;A, 620, A58 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...619A...2D/abstract"> 
 Planets around evolved intermediate-mass stars. II. Are there really planets around IC 4651 No. 9122, NGC 2423 No. 3, and NGC 4349 No. 127? </a> <br>  Delgado Mena et al. 2018,  A&amp;A, 619, A2 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...618A..42L/abstract"> 
 The TROY project. II. Multi-technique constraints on exotrojans in nine planetary systems </a> <br>  Lillo-Box et al. 2018,  A&amp;A, 618, A42 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018PASP..130i4202D/abstract"> 
 Chemical Abundances of Neutron-capture Elements in Exoplanet-hosting Stars </a> <br>  Delgado Mena et al. 2018,  PASP, 130, 094202 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018MNRAS.478.5240M/abstract"> 
 Recovering the colour-dependent albedo of exoplanets with high-resolution spectroscopy: from ESPRESSO to the ELT </a> <br>  Martins et al. 2018,  MNRAS, 478, 5240 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018JOSS....3..487F/abstract"> 
 kima: Exoplanet detection in radial velocities </a> <br>  Faria et al. 2018,  JOSS, 3, 487 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018NatAs...2..393S/abstract"> 
 An Earth-sized exoplanet with a Mercury-like composition </a> <br>  Santerne et al. 2018,  Nature Astronomy, 2, 393 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...611A...8S/abstract"> 
 Distinguishing the albedo of exoplanets from stellar activity </a> <br>  Serrano et al. 2018,  A&amp;A, 611, A8 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...609A..96L/abstract"> 
 The TROY project: Searching for co-orbital bodies to known planets. I. Project goals and first results from archival radial velocity </a> <br>  Lillo-Box et al. 2018,  A&amp;A, 609, A96 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018PASP..130i4202M/abstract"> 
 Chemical abundances of neutron-capture elements in exoplanet-hosting stars. </a> <br>  Mena et al. 2018,  PASP, 130, 9.4202 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...608A..94S/abstract"> 
 Constraining planet structure and composition from stellar chemistry: trends in different stellar populations </a> <br>  Santos et al. 2017,  A&amp;A, 608, A94 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...608A..25B/abstract"> 
 Precise masses for the transiting planetary system HD 106315 with HARPS </a> <br>  Barros et al. 2017,  A&amp;A, 608, A25 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...606A.107O/abstract"> 
 Understanding stellar activity-induced radial velocity jitter using simultaneous K2 photometry and HARPS RV measurements </a> <br>  Oshagh et al. 2017,  A&amp;A, 606, A107 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...603A..30S/abstract"> 
 Observational evidence for two distinct giant planet populations </a> <br>  Santos et al. 2017,  A&amp;A, 603, A30 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016OLEB...46..385F/abstract"> 
 A Pragmatic Bayesian Perspective on Correlation Analysis. The exoplanetary gravity - stellar activity case </a> <br>  Figueira et al. 2016,  OLEB, 46, 385 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A..87A/abstract"> 
 Abundance trend with condensation temperature for stars with different Galactic birth places </a> <br>  Adibekyan et al. 2016,  A&amp;A, 592, A87 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A.143F/abstract"> 
 Is the activity level of HD 80606 influenced by its eccentric planet? </a> <br>  Figueira et al. 2016,  A&amp;A, 592, A143 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A..13S/abstract"> 
 An extreme planetary system around HD 219828. One long-period super Jupiter to a hot-Neptune host star </a> <br>  Santos et al. 2016,  A&amp;A, 592, A13 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...591A..34A/abstract"> 
 ζ<SUP>2</SUP> Reticuli, its debris disk, and its lonely stellar companion ζ<SUP>1</SUP> Ret. Different T<SUB>c</SUB> trends for different spectra </a> <br>  Adibekyan et al. 2016,  A&amp;A, 591, A34 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...589A..25F/abstract"> 
 The HARPS search for southern extra-solar planets. XL. Searching for Neptunes around metal-poor stars </a> <br>  Faria et al. 2016,  A&amp;A, 589, A25 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...588A..31F/abstract"> 
 Uncovering the planets and stellar activity of CoRoT-7 using only radial velocities </a> <br>  Faria et al. 2016,  A&amp;A, 588, A31 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...585A.135M/abstract"> 
 The HARPS search for southern extra-solar planets. XXXIX. HD 175607, the most metal-poor G dwarf with an orbiting sub-Neptune </a> <br>  Mortier et al. 2016,  A&amp;A, 585, A135 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...583A..94A/abstract"> 
 Identifying the best iron-peak and α-capture elements for chemical tagging: The impact of the number of lines on measured scatter </a> <br>  Adibekyan et al. 2015,  A&amp;A, 583, A94 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...576A.134M/abstract"> 
 Evidence for a spectroscopic direct detection of reflected light from <ASTROBJ>51 Pegasi b</ASTROBJ> </a> <br>  Martins et al. 2015,  A&amp;A, 576, A134 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...573A.101M/abstract"> 
 BGLS: A Bayesian formalism for the generalised Lomb-Scargle periodogram </a> <br>  Mortier et al. 2015,  A&amp;A, 573, A101 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014A&A...570A..21F/abstract"> 
 Exoplanet hosts reveal lithium depletion. Results from a homogeneous statistical analysis </a> <br>  Figueira et al. 2014,  A&amp;A, 570, A21 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014ApJ...790..138V/abstract"> 
 Asteroseismic Estimate of Helium Abundance of a Solar Analog Binary System </a> <br>  Verma et al. 2014,  ApJ, 790, 138 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014A&A...566A..35S/abstract"> 
 The HARPS search for southern extra-solar planets. XXXV. The interesting case of HD 41248: stellar activity, no planets? </a> <br>  Santos et al. 2014,  A&amp;A, 566, A35 </li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2012AN....333..954F/abstract"> 
 On the possibility of using seismic probes to study the core composition in pulsating white dwarfs </a> <br>  Faria et al. 2012,  Astronomische Nachrichten, 333, 954 </li>


</ul>

</div>
