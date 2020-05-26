---
layout: post
lang: en
ref: blogpost
comments: true
title:  ESPRESSO finds Proxima b
author: joao
excerpt: " "
---

{% include image.html 
    url="/assets/img/planet_M_dwarf.jpg"
    description="Credit: ESO/M. Kornmesser"
%}

Back in 2016, the discovery[^1] of an exoplanet orbiting Proxima Centauri was a
groundbreaking result. Proxima is the closest star to the Sun, at a distance of
only 1.3 parsec, or 4.2 light-years from us. And Proxima *b*, the planet, has a
similar mass to that of the Earth, and orbits close to the habitable zone.

[^1]: The discovery paper can be found [here](https://arxiv.org/abs/1609.03449).

Now, the new ESPRESSO instrument[^2] was able to **independently confirm** the
presence of this planet and measure its mass with higher precision. ESPRESSO is
a new spectrograph installed at ESO's Very Large Telescope (VLT), in the Paranal
observatory. It can measure radial velocities with an unprecedented precision,
which allows to find very low mass planets, just like Proxima b.

[^2]: For more information about ESPRESSO, see [this](https://www.eso.org/sci/facilities/paranal/instruments/espresso.html) page.

Very soon, the instruments at the ELT will be able to look at Proxima b with 
new eyes, characterizing the atmosphere of the potentially habitable rocky planet.

<p style="text-align: center;">
<!-- See the <a href="#" target="_blank">press pelease</a> from IA -->
<!-- &nbsp; &mdash; &nbsp;  -->
Read <a href="https://arxiv.org/abs/2005.12114" target="_blank">the paper</a> on the ArXiv
</p> 


## The star

Astronomers call Proxima Centauri a red dwarf (or *M* dwarf). Its mass and
radius are smaller than the Sun's, by about a factor of eight. It has a very low
luminosity (even though it's so close) but, like other red dwarfs, its
brightness can sometimes increase dramatically because of magnetic activity. 
It cannot be seen with the naked eye, but it's there, next to α Cen A and B, the 
other two members of a triple system.


## The planet

The planet discovered around Proxima was called *Proxima b*, because
astronomers are incredibly inventive when naming things. The planet orbits the
star at a distance of roughly 0.05 AU[^3] (about 7.5 million km) with an orbital
period of about 11.2 Earth days. That is, a *year* on Proxima b takes 11.2 days.

[^3]: AU stands for Astronomical Unit. It is the average distance between the 
      Earth and the Sun. So the Earth orbits at 1 AU.

Proxima b is slightly more massive than the Earth (1.3 Earth masses) and we
think it is probably a rocky planet like ours. Even though it is much closer to
its host star, the temperature of Proxima b is estimated to be within the range
where water could exist in liquid form. We say that the planet is in the
habitable zone. But that doesn't mean it is inhabited! That, we don't know yet.


## The challenge of detection

Finding such low mass planets can be quite difficult. First, the amplitude of
the radial velocity effect the planet has on the star depends on the planet mass
and on the orbital period. More massive planets, like Jupiter and Saturn, create
radial velocity signals 100 times larger than lighter planets like the Earth and
Venus, even though they are much further away from the Sun. So it's easier to
detect more massive planets orbiting closer to their host stars. 

Proxima b is fairly close to its star, but it has a low mass. 
So, how could we detect it?

The answer is that the star is much less massive than the Sun. This means that
the planet, even with a mass close to that of the Earth, is able to "push" and
"pull" the star harder, resulting in a larger amplitude radial velocity signal.

Instead of the planet orbiting around the star, in reality both bodies actually
orbit the center of mass of the system. This means the star is moving back and
forth, towards and away from us. We observe a blueshift and a redshift of the
stellar light, by looking at its spectrum. If these variations are periodic, we
infer the presence of a planetary companion. This is the essence of the radial
velocity method.

One additional source of difficulties is the magnetic activity of the star. As
it rotates, every 83 days, big star spots at the stellar surface produce an
extra modulation in the observed radial velocities. Sometimes, this modulation
can be much larger than the signals caused by the planets. So we need to find
ways to correct for stellar activity if we want to find the lowest mass planets.

In this new study on Proxima b, we used something called Gaussian processes
(GP), a statistical tool that can model very well the activity-induced radial
velocity variations. I've been working on Gaussian process models for a few
years, but it's still very nice to see how much they can help us. In the figure
below, you can see the GP model together with the ESPRESSO radial velocities.
All these variations are caused by the star itself. The signal from the planet
sits *on top* of this activity signal.

![Proxima_GP]({{site.base_url}}/assets/img/proxima_GP.png)


But the new ESPRESSO observations are much more impressive when compared with
previous data from other instruments. Proxima b was first detected using HARPS,
another ESO instrument, situated in the La Silla observatory. HARPS used to be
the most precise planet-hunting spectrograph, allowing for the discovery of
hundreds of exoplanets. It is a truly impressive feat of engineering and human
endeavour that ESPRESSO can now achieve *much better* radial velocity precision.

In the figure below, you can compare the ESPRESSO observations (in green) with
the previous HARPS observations (in orange). The improvement is absolutely
staggering!


![Proxima_phase_curve]({{site.base_url}}/assets/img/proxima_phase_curve.png)


For some context: ESPRESSO is now measuring the radial velocity of Proxima with
a precision of 30 cm/s. This is about the same speed as a Galapagos tortoise can
move. What this means is that we are able to measure the velocity of a star,
about 40 *trillion* kilometers away from us, with a precision similar to the
speed of a giant tortoise!

## The future

This is only the first planet confirmed by ESPRESSO. We are currently observing
other stars, some like Proxima and others more akin to the Sun. I wouldn't be
surprised if, in a few months, I'm writing here to announce the discovery of an
Earth-like planet in the habitable zone of a Sun-like star. Exciting times ahead!


---