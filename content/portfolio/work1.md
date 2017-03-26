+++
showonlyimage = false
draft = false
image = "/img/portfolio/eyeHeadTracking/EyeTrackingScene.gif"
date = "2016-08-05T18:25:22+05:30"
title = "Character head and eye tracking"
weight = 1
+++

A script component that enables player tracking for a given character's eyes and head, based on parametrical constraints. 

<!--more-->

***

When you're working on a virtual environment with interactive characters it becomes increasingly clear that these interactions need to be as natural as possible. What's more, it's paramount when the main focus of your virtual experience is education. Imagine having a personal instructor that never looks at you when explaining things. You can imagine things start to get really awkward, right?  

One of the challenges faced by the **[Yeltic](http://yeltic.com/en/)** organization in their virtual trainings was exactly this: characters seemed to lack naturality when interacting with the player. 

#### The Solution

> I proposed and developed a solution to this problem: character head and eye tracking. With this technique, combined with corporal, facial animations, and lipsync, characters did really seem more lively, which in turn, made players less uncomfortable around their virtual instructors.

This of course, is nothing new. It's an aspect of npc characterization that has been in game development for long now. Think of how npcs looked at Link when approached in The Legend of Zelda: The Wind Waker, for instance.

![Killer bees][1]
<!-- ###### The Legend of Zelda: The Wind Waker is property of Nintendo -->

Starting with the basic idea of tracking, the first thought that comes to mind is transform's look at operations. We can easily align a transform's rotation to "look at" a given target. But this solution, unconstrained, can create weird looking results:

![Unconstrained tracking][2]

As you can see, when rotation is unconstrained, things start to look very unnatural. People cannot after all, turn their heads 180 degrees nor can their eyes rotate indefinitely (which ends up in incredibly spooky, scary results!). Another issue with the eyes was that each individual eye must have the same rotation as the other does, unless we want to end up with one eye looking at one direction and the other to somewhere else! Then, I broke this problem in two: 

* Make a single controller for both eyes which rotate them towards a given target and do not exceed a given angle.
* Make a controller for the head which rotates it towards a given target and does not exceed a given angle.

For the eyes' controller, I used a single center transform between them called EyesCenter. Then, I calculated the angle between the EyesCenter's forward vector and the target's distance vector relative to the EyesCenter. I used this calculated angle with an absolute operation to know if it was bigger than the maximum angle provided. If it wasn't, then the target was in range and the eyes would rotate according to the calculated angle (with a lerp smoothing function). Otherwise, the target was out of the provided range of vision and would return to a default orientation (in this case, I used an identity Quaternion).

It was very much the same for the head controller but simpler, since it would only need to modify only the head's transform.

#### The Result

A reusable character component which provides eye contact and head movement for a given target (supporting dynamic target changes), given as parameters: vision range angle, rotation speed, and rotation offset.  
![Inspector component][6]

Constrained head and eyes tracking with a default pose to return to when out of vision range.
![Constrained tracking][3]
Support for both horizontal and vertical tracking and constraints.
![Vertical movement][4]
Rotation constraints help to avoid unnatural behavior.
![Back movement][5]

It is worth acknowledging that this component has its limitations and may be improved on some aspects:

* Maybe it's not desirable to return to a default pose, maybe it would be better to leave the rotation as the last rotation when the target left the range of vision.
* It requires the character's avatar to be modified: no control bone for any of the eyes nor the head. This means that if there are any animations that animate these bones, those animations for said bones will be ignored.

This work was developed while working at Yeltic: http://yeltic.com/en/

[1]: /img/portfolio/eyeHeadTracking/killerbees.gif#center-resize "Remember these creepy little guys? Yikes!"
[2]: /img/portfolio/eyeHeadTracking/EyeTrackingNoConstraints.gif#center-resize "Unconstrained head tracking"
[3]: /img/portfolio/eyeHeadTracking/EyeTrackingOnOff.gif#center-resize "Constrained tracking with default position"
[4]: /img/portfolio/eyeHeadTracking/EyeTrackingUpDown.gif#center-resize "Vertical tracking"
[5]: /img/portfolio/eyeHeadTracking/EyeTrackingBack.gif#center-resize "Unnatural possessed head rotations no more!"
[6]: /img/portfolio/eyeHeadTracking/EyeTrackingInspector.gif#center-resize "Inspector component"
[7]: /img/portfolio/eyeHeadTracking/EyeTrackingScene.gif#center-resize "Scene capture"



