---
title: Premult
draft: false
tags:
---
## What's up with the *Premult*?

![[Pasted image 20230108133535.jpeg]]

One of the first mental hurdles when you first start compositing is understanding what a **Premult** is. I've seen students and juniors throw it around because they think they are supposed to. When in doubt, just throw in a Premult, right?

Before we talk about what a Premult is let's just quickly go over the concept of [[Alpha Mattes]], or VFX Cookie cutters, as I like to call them.

### Alpha Mattes

The image below is a sample green screen foreground to be composited over the background.

|                 Foreground                 |                 Background                 |
| :----------------------------------------: | :----------------------------------------: |
| ![[Pasted image 20230108134805.jpeg\|300]] | ![[Pasted image 20230108134826.jpeg\|300]] |

Using one of many techniques like [[Keying]] or [[Rotoscoping]], we can generate the Alpha Matte (a black and white image) we need to "cut out" the object we want to separate from the image. 

*In this case we want to separate the woman from the green background.*

Here is the result from [[Keying]]:

![[Pasted image 20230108140203.jpeg]]

So the Alpha Matte (black and white image) is good to go. What next?


## The Cookie Cutter

An Alpha Channel, in it's simplest explanations, is a cookie cutter.

![[Pasted image 20230108140645.jpeg]]

The flattened dough is the original image. In this example it's the woman on the green screen. The cookie cutter is your Alpha Matte (the black and white image). And when you press the Alpha Matte into your image, your cut it right out from the image so you can put it over your background!

## Quick Math

Our alpha mattes is made up of black and white pixels (and all shades of gray in between).

In math talk, white pixels have a value of 1, and black pixels have a value of 0.

So let's take a trip back to elementary school math.

What's: `5 x 1` ?

The answer is 5.

What's: `4535 x 1` ?

4535.

We all know that ANY variable times 1 will **ALWAYS** equal itself. 

$$ X*1=X$$

And any variable time 0 will **ALWAYS** be 0.

So... `17 Billion x 0 = 0`

$$ X*0=0$$

So what is happening when we take our Alpha Matte and apply it to our image? 
We're **MULTIPLYING** it.

Any pixels in our image that are multiplied by white pixels are used, and those multiplied by black pixels are removed. Leaving in place, a cookie cut image that we can now put on top of our background!!

![[Pasted image 20230108191347.jpeg]]

### So it's Multiplying... why is it called Premult?

Admittedly, I find this to be slightly misnamed, since what it's actually doing is multiplying your image with your alpha.

But back in the day, when images where passed to the compositing department, they came in two flavours: Premult or Straight. Straight was the image without the alpha baked right in, and Premult was with the alpha already baked in.

And much like that high school nick name you hated so much, the name kinda stuck.

The Premult node is Nuke's way of telling it to use the cookie cutter to make your cookie!



