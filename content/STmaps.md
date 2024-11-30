---
title: ST Maps
draft: false
tags:
---
A super cool tool that serves multiple uses in [Nuke](../Software/Nuke/Nuke.md)!

![[Pasted image 20220804195608.jpeg|400]]

First off, I'm not too sure what the ST stands for. Closest to an acceptable answer I heard was it was the next available set of letters after UV. 

So what is this? In a nut shell it's a fancy coordinate system, made up of a green ramp going across, and a red ramp going up.

**Each position on the image, regardless of format size, is associated to a certain value of the Green and Red ramp.**

![[Pasted image 20220804202131.jpeg|400]]

Green Ramp. 0 at the bottom, 1 up on top.

![[Pasted image 20220804202148.jpeg|400]]

Red Ramp. 0 on the left, 1 off to the right.

These two ramps make a coordinate system. Let's look at two of the corners.

The value in the upper left is the highest value of green, and the lowest of red.

![[Pasted image 20220804200027.jpeg]]

And in the lower right it's the highest value of red, with the lowest value of green

![[Pasted image 20220804200123.jpeg]]


---


![[Pasted image 20220804200352.jpeg]]

Here is an ST Map and a Checkerboard. By default nothing should happen.

But what if we rotated the STmap?

![[Pasted image 20220804200852.jpeg]]

We rotated the STmap, and the Checkerboard follow along for the ride. Why? Because when the STmap changed its orientation it's still the associating the original Green and Red pixels values to the original pixels of the checkerboard.

Each pixel of the checkerboard WANTS to follow the original Red and Green pixel value it was associate to. 

Since we rotate the whole STmap, the whole checkboard rotatated.

But what if we moved it? Scaled it?

![[Pasted image 20220804201652.jpeg]]

Each pixel of the checkerboard wants to stay attached to the original coordinate system, so it comes along for the ride.

So it's a fancy transform? Yes. But it does so much more, but like with anything you need to crawl before you can run.

---

Additional topics

[[Creating an ST Map]]

[[My Puppet Tool]]

