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
The ultimate goal is to find a planet like the Earth orbiting a star like the Sun.  
But that's not so easy. 
Low-mass planets (like the Earth, with a mere 6 septillion kg)
impact tiny effects on their host stars,
in particular changing their _radial velocity_ (RV) or their brightness. 
This is the basis of the RV 
(not [that](https://www.amazon.com/RV-Method-Improvisational-Scene-Building/dp/0986071447)) 
and transit (not [that](https://transitmethod.bandcamp.com/)) methods for planet detection.



{% include image.html 
    url="https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif"
    description="The idea behind the RV method. Credit: <a href='example.com'>NASA JPL</a>"
%}



<!-- <img src="https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif" alt="rvmethod" width="80%"/> -->

<!-- ![](https://dtm.carnegiescience.edu/sites/dtm/files/radial-velocity-GIF_postdoc-spotlight.gif) -->
<!-- *The idea behind the RV method. Credit: NASA JPL* -->

The whole problem boils down to finding periodic signals of very low amplitude
in radial velocity time series which can cover decades.

...

During my PhD, I was in charge of a radial-velocity survey of metal-poor stars, 
with the goal of estimating the occurrence rate of low-mass planets in the low metallicity regime.
I found a planet occurrence rate smaller than that of solar-metallicity stars,
which means that the famous giant planet -- metallicity correlation
also extends to the population of low-mass planets.



### Software

{% assign repos = site.github.public_repositories | where:"fork",false %}
{% assign disprepos = "kima,bgls,SAM,keplerian,iCCF" | split: "," %}
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
  either:
 - [%T](%u)  \n%10.1G  \n%Q \n\n 
  
  or:
 <li><a href="%u">%T</a> <br> %3.1G<br> %Q </li> \n

 would be useful to write a script...
-->


<!-- add <a name="tag"></a> to create a tag anywhere -->

### Publications <a title="permalink" href="{{site.baseurl}}/publications"><i class="fas fa-link fa-sm"></i></a>

I am co-author of {{ site.npapers }} refereed research papers.
Here is a complete list:

<div class="post-pubs">
<ul class="fa-ul">

<!-- python get_papers.py automatically creates research.md from a template file -->


<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2023MNRAS.519.5439C/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2023MNRAS.519.5439C">Modelling stellar activity with Gaussian process regression networks</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 519, issue 4, pp. 5439, 2023</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2023A%26A...670A...5S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2023A&A...670A...5S">Two temperate Earth-mass planets orbiting the nearby star GJ 1002</a> <br>Astronomy and Astrophysics, vol. 670, A5, 2023</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2023A%26A...669A..18B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2023A&A...669A..18B">KOBEsim: A Bayesian observing strategy algorithm for planet detection in radial velocity blind-search surveys</a> <br>Astronomy and Astrophysics, vol. 669, A18, 2023</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022A%26A...667A.102L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022A&A...667A.102L">The KOBE experiment: K-dwarfs Orbited By habitable Exoplanets. Project goals, target selection, and stellar characterization</a> <br>Astronomy and Astrophysics, vol. 667, A102, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022A%26A...666A.196A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022A&A...666A.196A">Automatic model-based telluric correction for the ESPRESSO data reduction software. Model description and application to radial velocity computation</a> <br>Astronomy and Astrophysics, vol. 666, A196, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022A%26A...665A.154B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022A&A...665A.154B">HD 23472: a multi-planetary system with three super-Earths and two potential super-Mercuries</a> <br>Astronomy and Astrophysics, vol. 665, A154, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022A%26A...663A.143S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022A&A...663A.143S">A novel framework for semi-Bayesian radial velocities through template matching</a> <br>Astronomy and Astrophysics, vol. 663, A143, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022AJ....163..171Z/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022AJ....163..171Z">The EXPRES Stellar Signals Project II. State of the Field in Disentangling Photospheric Velocities</a> <br>The Astronomical Journal, vol. 163, issue 4, pp. 171, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022MNRAS.511.3561T/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022MNRAS.511.3561T">BEBOP III. Observations and an independent mass measurement of Kepler-16 (AB) b - the first circumbinary planet detected with radial velocities</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 511, issue 3, pp. 3561, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022MNRAS.511.3571S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022MNRAS.511.3571S">BEBOP II: sensitivity to sub-Saturn circumbinary planets using radial-velocities</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 511, issue 3, pp. 3571, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2022A%26A...658A.115F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2022A&A...658A.115F">A candidate short-period sub-Earth orbiting Proxima Centauri</a> <br>Astronomy and Astrophysics, vol. 658, A115, 2022</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021CoBAO..68..447A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021CoBAO..68..447A">Composition of super-Earths, super-Mercuries, and their host stars</a> <br>Communications of the Byurakan Astrophysical Observatory, vol. 68, issue 2, pp. 447, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021Sci...374..330A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021Sci...374..330A">A compositional link between rocky exoplanets and their host stars</a> <br>Science, vol. 374, issue 6565, pp. 330, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...654A..60L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...654A..60L">HD 22496 b: The first ESPRESSO stand-alone planet discovery</a> <br>Astronomy and Astrophysics, vol. 654, A60, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...653A..41D/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...653A..41D">Warm terrestrial planet with half the mass of Venus transiting a nearby star</a> <br>Astronomy and Astrophysics, vol. 653, A41, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...653A..78D/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...653A..78D">The SOPHIE search for northern extrasolar planets. XVIII. Six new cold Jupiters, including one of the most eccentric exoplanet orbits</a> <br>Astronomy and Astrophysics, vol. 653, A78, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021MNRAS.503.5504C/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021MNRAS.503.5504C">Scheduling strategies for the ESPRESSO follow-up of TESS targets</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 503, issue 4, pp. 5504, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...649A.111A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...649A.111A">Stellar clustering and orbital architecture of planetary systems</a> <br>Astronomy and Astrophysics, vol. 649, A111, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...646A.158T/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...646A.158T">ESPRESSO high-resolution transmission spectroscopy of WASP-76 b</a> <br>Astronomy and Astrophysics, vol. 646, A158, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2021A%26A...645A..96P/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2021A&A...645A..96P">ESPRESSO at VLT. On-sky performance and first results</a> <br>Astronomy and Astrophysics, vol. 645, A96, 2021</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...644A..51S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...644A..51S">Broadband transmission spectroscopy of HD 209458b with ESPRESSO: evidence for Na, TiO, or both</a> <br>Astronomy and Astrophysics, vol. 644, A51, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...642A.121L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...642A.121L">Planetary system LHS 1140 revisited with ESPRESSO and TESS</a> <br>Astronomy and Astrophysics, vol. 642, A121, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...642A..31D/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...642A..31D">A precise architecture characterization of the π Mensae planetary system</a> <br>Astronomy and Astrophysics, vol. 642, A31, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...642A.182A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...642A.182A">Benchmark stars, benchmark spectrographs. Detailed spectroscopic comparison of ESPRESSO, PEPSI, and HARPS data for Gaia benchmark stars</a> <br>Astronomy and Astrophysics, vol. 642, A182, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020oeps.book..189S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020oeps.book..189S">Detection and Characterization Methods of Exoplanets</a> <br>Oxford Research Encyclopedia of Planetary Science, vol. None, 189, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...639A..77S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...639A..77S">Revisiting Proxima with ESPRESSO</a> <br>Astronomy and Astrophysics, vol. 639, A77, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...639A..35H/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...639A..35H">The correlation between photometric variability and radial velocity jitter. Based on TESS and HARPS observations</a> <br>Astronomy and Astrophysics, vol. 639, A35, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020MNRAS.493.5928S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020MNRAS.493.5928S">Can we detect the stellar differential rotation of WASP-7 through the Rossiter-McLaughlin observations?</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 493, issue 4, pp. 5928, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...635A..13F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...635A..13F">Decoding the radial velocity variations of HD 41248 with ESPRESSO</a> <br>Astronomy and Astrophysics, vol. 635, A13, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...635L...8A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...635L...8A">Can planetary rings explain the extremely low density of HIP 41378 f?</a> <br>Astronomy and Astrophysics, vol. 635, L8, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020AJ....159...73N/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020AJ....159...73N">Quantifying the Bayesian Evidence for a Planet in Radial Velocity Data</a> <br>The Astronomical Journal, vol. 159, issue 2, pp. 73, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2020A%26A...634A..75B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2020A&A...634A..75B">Improving transit characterisation with Gaussian process modelling of stellar variability</a> <br>Astronomy and Astrophysics, vol. 634, A75, 2020</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A..90L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019A&A...631A..90L">Exoplanet characterisation in the longest known resonant chain: the K2-138 system seen by HARPS</a> <br>Astronomy and Astrophysics, vol. 631, A90, 2019</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2019MNRAS.489.5764P/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019MNRAS.489.5764P">Gaussian process modelling of granulation and oscillations in red giant stars</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 489, issue 4, pp. 5764, 2019</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...630A.135U/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019A&A...630A.135U">Beyond the exoplanet mass-radius relation</a> <br>Astronomy and Astrophysics, vol. 630, A135, 2019</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2019MNRAS.485.3981S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019MNRAS.485.3981S">The metallicity-period-mass diagram of low-mass exoplanets</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 485, issue 3, pp. 3981, 2019</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...621A.110B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2019A&A...621A.110B">The GAPS Programme with HARPS-N at TNG. XVIII. Two new giant planets around the metal-poor stars HD 220197 and HD 233832</a> <br>Astronomy and Astrophysics, vol. 621, A110, 2019</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...620A..58S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...620A..58S">SWEET-Cat updated. New homogenous spectroscopic parameters</a> <br>Astronomy and Astrophysics, vol. 620, A58, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018JOSS....3..667G/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018JOSS....3..667G">ACTIN: A tool to calculate stellar activity indices</a> <br>The Journal of Open Source Software, vol. 3, issue 31, pp. 667, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...619A...2D/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...619A...2D">Planets around evolved intermediate-mass stars. II. Are there really planets around IC 4651 No. 9122, NGC 2423 No. 3, and NGC 4349 No. 127?</a> <br>Astronomy and Astrophysics, vol. 619, A2, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...619A.150O/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...619A.150O">Activity induced variation in spin-orbit angles as derived from Rossiter-McLaughlin measurements</a> <br>Astronomy and Astrophysics, vol. 619, A150, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...618A..42L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...618A..42L">The TROY project. II. Multi-technique constraints on exotrojans in nine planetary systems</a> <br>Astronomy and Astrophysics, vol. 618, A42, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018PASP..130i4202D/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018PASP..130i4202D">Chemical Abundances of Neutron-capture Elements in Exoplanet-hosting Stars</a> <br>Publications of the Astronomical Society of the Pacific, vol. 130, issue 991, pp. 094202, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018MNRAS.478.5240M/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018MNRAS.478.5240M">Recovering the colour-dependent albedo of exoplanets with high-resolution spectroscopy: from ESPRESSO to the ELT</a> <br>Monthly Notices of the Royal Astronomical Society, vol. 478, issue 4, pp. 5240, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018JOSS....3..487F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018JOSS....3..487F">kima: Exoplanet detection in radial velocities</a> <br>The Journal of Open Source Software, vol. 3, issue 26, pp. 487, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018NatAs...2..393S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018NatAs...2..393S">An Earth-sized exoplanet with a Mercury-like composition</a> <br>Nature Astronomy, vol. 2, 393, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...611A...8S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...611A...8S">Distinguishing the albedo of exoplanets from stellar activity</a> <br>Astronomy and Astrophysics, vol. 611, A8, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018A%26A...609A..96L/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018A&A...609A..96L">The TROY project: Searching for co-orbital bodies to known planets. I. Project goals and first results from archival radial velocity</a> <br>Astronomy and Astrophysics, vol. 609, A96, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018ASSP...49..267B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018ASSP...49..267B">Tutorial: Detecting Planetary Transits and Radial-Velocity Signals</a> <br>Asteroseismology and Exoplanets: Listening to the Stars and Searching for New Worlds, vol. 49, 267, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2018ASSP...49..165S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2018ASSP...49..165S">Exoplanetary Science: An Overview</a> <br>Asteroseismology and Exoplanets: Listening to the Stars and Searching for New Worlds, vol. 49, 165, 2018</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2017A%26A...608A..94S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...608A..94S">Constraining planet structure and composition from stellar chemistry: trends in different stellar populations</a> <br>Astronomy and Astrophysics, vol. 608, A94, 2017</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2017A%26A...608A..25B/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...608A..25B">Precise masses for the transiting planetary system HD 106315 with HARPS</a> <br>Astronomy and Astrophysics, vol. 608, A25, 2017</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2017A%26A...606A.107O/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...606A.107O">Understanding stellar activity-induced radial velocity jitter using simultaneous K2 photometry and HARPS RV measurements</a> <br>Astronomy and Astrophysics, vol. 606, A107, 2017</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2017A%26A...603A..30S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2017A&A...603A..30S">Observational evidence for two distinct giant planet populations</a> <br>Astronomy and Astrophysics, vol. 603, A30, 2017</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016OLEB...46..385F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016OLEB...46..385F">A Pragmatic Bayesian Perspective on Correlation Analysis. The exoplanetary gravity - stellar activity case</a> <br>Origins of Life and Evolution of the Biosphere, vol. 46, issue 4, pp. 385, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...592A..87A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A..87A">Abundance trend with condensation temperature for stars with different Galactic birth places</a> <br>Astronomy and Astrophysics, vol. 592, A87, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...592A.143F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A.143F">Is the activity level of HD 80606 influenced by its eccentric planet?</a> <br>Astronomy and Astrophysics, vol. 592, A143, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...592A..13S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...592A..13S">An extreme planetary system around HD 219828. One long-period super Jupiter to a hot-Neptune host star</a> <br>Astronomy and Astrophysics, vol. 592, A13, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...591A..34A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...591A..34A">ζ<SUP>2</SUP> Reticuli, its debris disk, and its lonely stellar companion ζ<SUP>1</SUP> Ret. Different T<SUB>c</SUB> trends for different spectra</a> <br>Astronomy and Astrophysics, vol. 591, A34, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...589A..25F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...589A..25F">The HARPS search for southern extra-solar planets. XL. Searching for Neptunes around metal-poor stars</a> <br>Astronomy and Astrophysics, vol. 589, A25, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...588A..31F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...588A..31F">Uncovering the planets and stellar activity of CoRoT-7 using only radial velocities</a> <br>Astronomy and Astrophysics, vol. 588, A31, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2016A%26A...585A.135M/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2016A&A...585A.135M">The HARPS search for southern extra-solar planets. XXXIX. HD 175607, the most metal-poor G dwarf with an orbiting sub-Neptune</a> <br>Astronomy and Astrophysics, vol. 585, A135, 2016</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2015A%26A...583A..94A/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...583A..94A">Identifying the best iron-peak and α-capture elements for chemical tagging: The impact of the number of lines on measured scatter</a> <br>Astronomy and Astrophysics, vol. 583, A94, 2015</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2015A%26A...576A.134M/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...576A.134M">Evidence for a spectroscopic direct detection of reflected light from <ASTROBJ>51 Pegasi b</ASTROBJ></a> <br>Astronomy and Astrophysics, vol. 576, A134, 2015</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2015A%26A...573A.101M/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2015A&A...573A.101M">BGLS: A Bayesian formalism for the generalised Lomb-Scargle periodogram</a> <br>Astronomy and Astrophysics, vol. 573, A101, 2015</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2014A%26A...570A..21F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014A&A...570A..21F">Exoplanet hosts reveal lithium depletion. Results from a homogeneous statistical analysis</a> <br>Astronomy and Astrophysics, vol. 570, A21, 2014</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2014ApJ...790..138V/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014ApJ...790..138V">Asteroseismic Estimate of Helium Abundance of a Solar Analog Binary System</a> <br>The Astrophysical Journal, vol. 790, issue 2, pp. 138, 2014</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2014A%26A...566A..35S/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2014A&A...566A..35S">The HARPS search for southern extra-solar planets. XXXV. The interesting case of HD 41248: stellar activity, no planets?</a> <br>Astronomy and Astrophysics, vol. 566, A35, 2014</li>
<li><a target="_blank" href="https://ui.adsabs.harvard.edu/link_gateway/2012AN....333..954F/EPRINT_PDF"><span class="fa-li"><i class="fas fa-file-pdf"></i></span></a><a target="_blank" href="https://ui.adsabs.harvard.edu/abs/2012AN....333..954F">On the possibility of using seismic probes to study the core composition in pulsating white dwarfs</a> <br>Astronomische Nachrichten, vol. 333, issue 10, pp. 954, 2012</li>


</ul>

</div>
