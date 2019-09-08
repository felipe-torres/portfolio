+++
date = "2016-09-05T19:41:01+05:30"
title = "Shader: Texture Blending"
draft = false
image = "/img/portfolio/textureBlending/TextureBlendingDemo_sm.gif"
showonlyimage = false
weight = 7
categories = ["gameplay"]
+++

A Unity3D shader that blends between two given textures and applies an optional tint color to them. Used primarily for special effects and texture transitioning.

<!--more-->

![Texture Blending][1]

***

I developed this simple shader in Unity3D at **[Yeltic](http://yeltic.com/en/)** as a solution for these problems:

* We had a scene with all baked lights, targeted for mobile. Which meant, no dynamic lights or shadows could be used.
* We needed some way to "transition" a material's texture for another. It was undesirable to simply swap textures at runtime. This particular effect was used as a means to transition between lightmaps and also to "animate" clothing textures getting wet.  

I created also a component to easily animate materials using this shader, so we could achieve some ambient effects for the scene.

This way, we could transition to and from different colors:
![Texture Blending][2]

And also textures:
![Texture Blending][4]

This work was developed while working at **Yeltic**: http://yeltic.com/en/

[1]: /img/portfolio/textureBlending/TextureBlending.gif#center-resize "Texture blending component"
[2]: /img/portfolio/textureBlending/TextureBlendingColors.gif#center-resize "Texture blending with colors"
[3]: /img/portfolio/textureBlending/TextureBlendingDemo.gif#center-resize "Detailed view of the scene"
[4]: /img/portfolio/textureBlending/TextureBlendingTextures.gif#center-resize "Texture blending"