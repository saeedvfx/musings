---
title: Colour Balance
draft: false
tags:
---

Balancing your shots is an important part of the work we do. Because different shots of the same scene can be shot under different lighting conditions, the sequence won't feel unified. One shot will be too underexposed. One too bright. One was using a different lighting setup all together. 

These all need to be **balanced** so the scene can flow seamlesssly.

For this example I'll use the following images:

![[wb_girl.jpg]]

(Alex1ruff, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons)


The first image is our **neutral** image. The second was shot with a warm light, and the third with a cool.

Here's one way we can balance the images in Nuke, and for the sake of this example we're going to pretend the [[Colour Checker]] isn't in the images.

---

Let's sample a portion of the wall behind her.

![[Pasted image 20220823195021.jpeg]]

The [Luminocity](Luminance) of the area is `0.127` with an RGB of ( .129 , .126 , .139)

---

Now let's take a sample of the same area in the warm image.

![[Pasted image 20220823194729.jpeg]]

The [Luminocity](Luminance) of the area is `0.156` with an RGB of ( .157 , .160 , .107)

In [Nuke](../Software/Nuke/Nuke.md) let's add a [[Grade Node]]. 

![[Pasted image 20220823195304.jpeg]]

We are going to spend all our time in the [[gain]].

![[Pasted image 20220823195551.jpeg]]

The Luminosity of the warm image was `.156` while the neutral was `.126`

So we need to [[gain]] our image **down**.

Slowly nudging the value lower we can see the luminosity of our warm image change in real time (assuming you still have the area selected from before).

I lowered the value until my luminosity was about `.127` which was a [[gain]] value of about `.91`

![[Pasted image 20220823200121.jpeg]]

The luminosity is much closer, but the image still feels warm. Now we hit the individual colour channels.

---

Click the Number 4 to the right to expand the [[gain]] so we see the individual channels.

![[Pasted image 20220823200246.jpeg]]

We're now going to repeat the same step for the Red, the Green, and the Blue.

We need to lower our Red so that the original value we recorded of `.157` is brought down to `.129`

Nudging the value lower I could see my red value go down until I landed at about `.129`

![[Pasted image 20220823200538.jpeg]]

Now we match the value of the Neutral green of `.126`. In this case, I'll need to raise the green in order to reach the value I want.

![[Pasted image 20220823200832.jpeg]]

Last step. Match the Blue to `.139`

![[Pasted image 20220823201048.jpeg]]

In this case I had to go to a value of 2.1 in the Blue in order to bring it back to `.139`.

---

Now let's look at our results.

![[Pasted image 20220823201444.jpeg]]

To the left we have the neutral, followed by the warm, with the neutralized warm image at the right.

And while it's not a perfect match (her skin tones have lost all their warmth, and the shirt has gone a little blue) it's definitely a step in the right direction to balancing the image.