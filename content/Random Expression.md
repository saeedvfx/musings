---
title: Random Expressions
draft: false
tags:
  - Nuke
---
Many times you'll be animating specific keyframes into Nuke. But once in a while you'll need to generate a random pattern. 

Like the following curve:

![[Pasted image 20240629153854.jpg]]

Here we see curve going nuts between 0 and 1, which we can use elsewhere in our script.

This curve is created with the default expression: 

	(random(1,frame*1)*1)+0

---

To create our random curve, create a node (I used a Multiply for this example) and go into the Animation Menu (the button with the Curved Line), drop down to Edit Expression, and paste the expression right in.

![[Pasted image 20240629154139.jpg]]

![[Pasted image 20240629154415.jpg]]

And now your value will be randomized and resemble the randomness of the curve we saw above.

![[Pasted image 20240629154515.jpg]]

---

Let's make some tweaks to our curve...

To do that let's take another look at our expression:

$$
(random(1,frame*1)*1)+0
$$

There's four elements in here we can change

- `1` = is the seed
- `frame*1` = is the Frequency (or Speed as I like to call it)
- `*1` = is the Amplitude (or Range as I prefer to think of it)
- `+ 0` =  is the value offset (or the Push-Up!)

Let's look at each one.

Let's say we want to slow down our curve!

We would have to affect the speed part of our expression. So let's see what happens when we change `frame*1` to `frame*.5`

$$
(random(1,frame*.5)*1)+0
$$

![[Pasted image 20240629162814.jpg]]

Our curves are spread out. Let's go extreme and change the speed to `frame*.1`

![[Pasted image 20240629162920.jpg]]

Hot dog!!

Let's say I want to increase my range, so instead of generating a random curve between 0 and 1, we go to a taller curve between 0 and 5!

We would now need to tweak the Amplitude (fancy word for RANGE between the high point and low point of the curve.)

Let's change the `*1` to `*5`

$$
(random(1,frame*1)*5)+0
$$

![[Pasted image 20240629164352.jpg]]

Check out those numbers on the left! Our range is between 0 and 5.
Let's go to 0 and 100!!

Let's change the Range to `*100`

$$
(random(1,frame*1)*100)+0
$$

![[Pasted image 20240629164603.jpg]]

Are we starting to see a pattern here?

---

We can control the vertical!
We can control the horizontal!

But what if we need a range between 50 and 150? How do we keep this curve from going all the way down to zero? We push it up!!

Enter the Value offset: `+0`

Originally it was at 0. So nothing happens. Let's add 50!

$$
(random(1,frame*1)*100)+50
$$

![[Pasted image 20240629164939.jpg]]

Check out that gap!!

Now what if we wanted between Negative 50 and positive 50??

(You know what's coming...)

$$
(random(1,frame*1)*100)-50
$$

![[Pasted image 20240629165115.jpg]]

So instead of pushing it up, we push it down!

---

And last, but not least, is the first number of the equation, our Seed: `1`

All that does is create a new curve with the same speed and range we decided.

You can put ANY value in there and you will get a complete new Random curve!

---

Special thanks to Victor Perez Nukepedia article, [The Random Expression](https://www.nukepedia.com/written-tutorials/the-random-expression).
