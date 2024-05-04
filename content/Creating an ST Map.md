---
title: Creating an ST Map
draft: false
tags:
  - Nuke
---

Using an expression node you can creat an ST Map using the follow equation in the red and green channel.

![[Pasted image 20220804202836.jpeg|500]]

But what's up with the `+.5` ?

At first I always used to put `x/width` in the Red and `y/height` in the Green.

But it was brought to my attention that the STmap would ever so slightly alter my image, even if there was no transform happening.

---
Here is a base STmap setup

![[Pasted image 20220806104832.jpeg]]

Here is a closeup view of the checkerboard directly.

![[Pasted image 20220806104805.jpeg]]

But looking at it through the STmap, with **no tranformations** yields this result.

![[Pasted image 20220806104959.jpeg]]

The pixels have been offset by half a pixel. Why?

From what I was told is that by default the `x/width`, `y/height` defaults the STmap into the lower left corner of the image. As seen by the red dot below.

![[Pasted image 20220806105430.jpeg]]

However for the STmap to properly lineup it needs to start at the centre of the first lower left pixel.

So we need to add `.5` to the X and Y which gives us:

`(x+.5)/width` & `(y+.5)/height` and now our STmap will line up.

Happy Days.

---
