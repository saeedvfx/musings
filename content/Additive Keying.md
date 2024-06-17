---
title: How to publish Obsidian notes with Quartz on GitHub Pages
draft: true
tags:
---


Here's a common task:

Take your plate (as seen below)

![](8F5MUR9X.jpg)
*Image from [Shotdeck](https://shotdeck.com/)*

and replace the background with something completely different, like this

![](PJDMGA2P.jpg)
*Image from [Shotdeck](https://shotdeck.com/)*

Your first reaction is to roto your actor to create the alpha you need to put him over the new background. But that hair...

Yes, you might have to roto some of it, and a luma might get you a decent core, but to get those curly wispies back in you'll need a little help from additive keyer. 

Nuke doesn't give you one by default so here is how you can roll your own.

![](Pasted%20image%2020220722215558.jpg)

A simple plus can give you an idea of what you could expect, but this just the beginning. 

# Step 1 : Create a clean plate

For the our purposes we need to recreate a clean plate as close to original footage as possible. In this case we could use a constant that closely matches sky, but let's use some comp math and work some magic.

First thing we should do is make sure our plate has an alpha of 1. If it doesn't just add one quickly with a shuffle node.

![](Pasted%20image%2020220722221200.jpg)

Let's create a roto shape around our actor's head and stencil it out from the plate. 
![](Pasted%20image%2020220722220928.jpg)

We now have our main plate with a hole taking out all the uncessariy detail out of the image so that we can create our clean sky.

![](Pasted%20image%2020220722221029.jpg)

Now I can roll my own [[edge extruder]] and create a clean plate of the back ground.

(I will explain what is happening with the edge extruder at a later date)

![](Pasted%20image%2020220722221442.jpg)


# Step 2: Take it into LOG

Now for the next step we need to convert all our elements into [[LOG Space]]. 

![](Pasted%20image%2020220722221635.jpg)

There's that lifted LOG space look. But for the math to work better we need to be here.

# Step 3: Super simple math (I promise)

Next we DIVIDE our main plate (in LOG space) by our clean plate (also in LOG)

![](Pasted%20image%2020220722221845.jpg)

We then take the results and now MULTIPLY that over our Background in (you guessed it) LOG Space. And we start to get something interesting.

![](Pasted%20image%2020220722222006.jpg)


# Step 4: Back to Linear

Now for the final step we take our results and convert from LOG back in the LINEAR, and we get this!

![](Pasted%20image%2020220722222104.jpg)

Our original background colour is coming through, and we're getting a great amount of hair detail.

And the face, you might ask? Well that you can do with roto... but at least you have the hardest part of the hair already done for you, and that right there is most of the battle.

---

So what is going on here exactly?

(Answer coming soon)