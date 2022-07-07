+++
draft = false
image = "/img/portfolio/highwayGenerator/PathGeneration_AirView.gif"
showonlyimage = false
date = "2016-12-05T19:50:47+05:30"
title = "Procedural highway generator"
weight = 3
categories = ["gameplay"]
+++

Procedural generation of a highway given an array of modules in Unity.

<!--more-->

![Highway generation skyview][1]

***

#### The Problem

This feature was requested for a VR experience where the player needed to be seated on the back of a pickup moving along a highway, for an indefinite amount of time.

> I developed this generator to procedurally build a highway from a set of modular prefabs. 

As stated above, the solution needs a group of '*modular prefabs*'. These modules need to have a common origin pivot, so the pieces can connect to each other successfully. For example:
![Module examples][2]
As seen above, each highway piece can have a turning angle. This generator takes these angles into account when connecting together the modules, automatically aligning them according to the last generated piece. Also, each module is given a probability value, to make some modules more likely to appear than others. With this, modules wouldn't "collide" with each other (for example, by spawning multiple turns to the same side).

![Generation 3rd person][4]
The next step was to make the pickup actually traverse the road. To do this, I made a controller that uses waypoints in conjunction with the incredible plugin **[DOTween](http://dotween.demigiant.com/)** (Get it, it's awesome and free!).

As you can see from the next image, the generator maintains a (configurable) maximum amount of modules at all times, attaching new modules forward, and destroying modules on the back. It also keeps the player on the middle, so that this creation/destruction is not visible to him. 
![Generation sceneview][5]

On the next image you can see the results from a VR perspective running on Occulus, with final lighting settings and models.
![Generation ingame][3]

This work was developed while working at **Yeltic**: http://yeltic.com/en/

[1]: /img/portfolio/highwayGenerator/PathGeneration_AirView.gif#center-resize "Generation skyview"
[2]: /img/portfolio/highwayGenerator/Modules.jpg#center-resize "Module examples"
[3]: /img/portfolio/highwayGenerator/Recorrido_FinalLook.gif#center-resize "Generation ingame"
[4]: /img/portfolio/highwayGenerator/PathGeneration_Game.gif#center-resize "Generation 3rd person"
[5]: /img/portfolio/highwayGenerator/PathGeneration_Scene.gif#center-resize "Generation sceneview"