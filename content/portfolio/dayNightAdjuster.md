+++
draft = false
image = "/img/portfolio/dayNightAdjuster/dayNightAdjuster.png"
showonlyimage = false
date = "2016-08-05T19:50:47+05:30"
title = "Day night adjuster"
weight = 10
categories = ["gameplay"]
+++

A reusable Unity component to create lighting setting profiles for day or night.

<!--more-->

***

This component was created to enable the lighting artist to create two lighting profiles: one for the day and one for the night. After the profiles were created, different lighting settings could be loaded on the scene depending on the time of day desired.

![Additive scene loader][1]

The component takes into account:

* Skybox
* Dynamic lights used during each profile
* Directional light rotation, intensity and color
* Fog color and density
* Emissive materials
* Tonemapping settings

Day:
![Day][2]

Night:
![Night][3]

This work was developed while working at **Yeltic**: http://yeltic.com/en/

[1]: /img/portfolio/dayNightAdjuster/dayNightAdjuster.png#center-resize "Day night adjuster component"
[2]: /img/portfolio/dayNightAdjuster/dayNightAdjuster_day.gif#center-resize "Scene during day"
[3]: /img/portfolio/dayNightAdjuster/dayNightAdjuster_night.gif#center-resize "Scene during night"

