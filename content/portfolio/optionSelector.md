+++
draft = false
image = "/img/portfolio/optionSelector/optionSelector_bullying_sm.gif"
showonlyimage = false
date = "2016-10-05T19:50:47+05:30"
title = "VR: Option Selector component"
weight = 5
categories = ["gameplay"]
tags = ["ui"]
+++

Different Unity components for displaying an array of options in a VR environment

<!--more-->

#### World-Space Pop option selector

![World-Space Pop option selector][2]

> I developed this UI component for instances where the user needs to choose one of multiple options while needing to be aware of the rest. 

For this specific version, all options are shown at all times. Answers are located to where the relevant action takes place. The user can look around the stage for the options and choose them using a reticle input. 

During development, the developer defines each option content and action associated to it (a Unity Event) and may choose a prefab to instantiate for each option. The developer can also choose the number of options they like and their positions in world space.

***

#### Single option selector

![Single option selector][1]

> I developed this UI component for instances where the user needs to choose one of multiple options. 

For this specific version, a single option is shown at any time. The user can scroll through the options and choose them using configurable inputs. 

During development, the developer defines each option content and action associated to it (a Unity Event) and may choose a prefab to instantiate for each option. The developer can also choose whether to include a response timer or not, and configure the time the user has to choose an option. The developer may also include a default action that occurs if time runs out before the user chooses.

This work was developed while working at **Yeltic**: http://yeltic.com/en/

[1]: /img/portfolio/optionSelector/SingleOptionSelector.gif#center-resize "Single option selector"
[2]: /img/portfolio/optionSelector/optionSelector_bullying.gif#center-resize "World-space option selector"