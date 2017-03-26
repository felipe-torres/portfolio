+++
draft = false
image = "img/portfolio/additiveSceneLoader/AdditiveSceneLoader_Comparison_2.jpg"
showonlyimage = false
date = "2016-08-05T19:50:47+05:30"
title = "Optimization: Additive scene loader"
weight = 4
+++

A reusable Unity component to use in conjunction with the Cinema Director timeline to additively load scenes in Unity.

<!--more-->

![Additive scene loader][1]

***

#### The Problem

One of the constraints we had for a project was that it needed to be ran in an iPhone 5 with stereoscopic vision enabled (Google Cardboard). This meant we only had to 1gb of RAM to work with and, since all our environment was 3D and contained many audio and graphical assets, several steps were taken to assure it worked as smoothly as possible, without any memory leaks or crashes.

After optimizing all assets as much as possible, without compromising too much quality, the app ran smoothly, but would suddenly crash. After memory monitoring both in the Unity profiler and in the Instruments application on Mac, it was clear too many assets were loaded into memory.

#### The Solution

> I designed and developed a solution to split our interactions and scene structure in different scenes to reduce the overall number of assets loaded in memory.

This solution comprised the loading and unloading of scenes, both additively and asynchronously, to be as unnoticeable to the user as possible (keeping loading times as short as could be achieved).

After splitting the project in additive scenes, the app suffered no longer from memory crashes on the device.

Profiler comparison before and after applying this optimization is as follows:

* Textures reduced from 231.9 MB to 190.2 MB
* Meshes reduced from 79.4 MB to 58.6 MB
* AudioClips reduced from 139.3 MB to 69.1 MB
* Number of objects in scene reduced from 114115 to 5244
* Game Objects in scene reduced from 4528 to 1637

Before:
![Before][2]

After:
![After][3]

This work was developed while working at **Yeltic**: http://yeltic.com/en/

[1]: /img/portfolio/additiveSceneLoader/AdditiveSceneLoader.jpg#center-resize "Additive loader component"
[2]: /img/portfolio/additiveSceneLoader/AdditiveSceneLoader_Comparison_1.jpg#center-resize "Before additive loader"
[3]: /img/portfolio/additiveSceneLoader/AdditiveSceneLoader_Comparison_2.jpg#center-resize "After additive loader"

