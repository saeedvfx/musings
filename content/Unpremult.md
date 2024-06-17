---
title: Unpremult
draft: false
tags: []
---
The bulk of our work is combing alphas and images to create cut out image sequences to layer on top of work. This process is known as [Premulting](Premult)

Looking at the following we see a simple example of a [Premulted Image](Premult).

![[Pasted image 20240615221227.jpg|400]]

It started with a checkerboard...
![[Pasted image 20240615221140.jpg|400]]

Multiplyed by this lovely alpha...
![[Pasted image 20240615221206.jpg|400]]

Gives us:
![[Pasted image 20240615221227.jpg|400]]

But like any good math equation, we can also go in REVERSE!

---

Let's say $$ 2 *5 = ? $$
The answer we know is 10

And we go backwards?
$$ 10 ÷ 5 = ? $$
Goes back to 2

---

So let's go backwards with our comps and DIVIDE our results with the alpha. Only the process isn't called Divide (because that would make too much sense), it's known as an Unpremult. The reverse of of the [[Premult]].


![[Pasted image 20240615221548.jpg]]

The unpremult has removed the alpha and exposed our pixels. 

![[Pasted image 20240615221718.jpg]]

What just happened here? Simple Math.

Every pixel in our image was divided by the Alpha value of itself.

Every pixel that has an alpha value of 1 ends up with 1.

$$ 1 ÷ 1 = 1 $$ 

So a transparent pixel down near the bottom probably has an alpha value of about .2

$$ .2 ÷ .2 = 1 $$
And now it has a pixel value of one, and the transparency effect is gone!!


Any value divided by itself will aways equal 1

$$ x ÷ x = 1 $$
But why this new egg shape, and not the original full checkerboard, you might ask?

Remember when you multiply ANY number by 0 you get 0? Well, any number divided by 0 gives an undefined number. Which is a fancy way of saying ZILCH!!

Any pixel that has an alpha of zero is pretty much gone in this branch of our script.

![[Alpha_unpremult.jpg]]

This is useful to know for things such [[Edge Extruders]]