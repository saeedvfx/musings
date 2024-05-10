---
title: Shuffle Node
draft: false
tags:
  - Nuke
---
Admittedly, I wasn't a huge fan, at first, of the new Shuffle node. But I saw how handy it was when it came to shuffling extra channels in.

---

Let's say you have a client or fellow artist that wants to include a few extra mattes (beyond the standard alpha) into your latest render. Be it for colour correction, or some other wild reason.

You sometimes want to carry more than just your your standard RGBA in your EXR file.

For this example the client has a checkerboard in their RGB channel and wants to include extra channels baked into the file so the colourist can have extra control in DI session.

---

On the left we have the 3 extra channels we want to include into our RGB on the right. We can merge them all with a Shuffle.

![](Pasted%20image%2020220815210511.png)



![](Pasted%20image%2020220815210715.png)

Here is a look inside:

![](Pasted%20image%2020220815205810.png)

We can see the left side has an `In` going into the B. With the RGBA being piped through, so at the end we get the checkerboard. 

But look at the colour tiles and see what they are going into the Shuffle via the A pipe. We need to let Shuffle node know we want to use that.

In the second box below change your B input in A. It will know to be looking at what we piped in; the three coloured tiles.

![](Pasted%20image%2020220815211000.png)

Because in this example our three tiles are using the R, G, and B channels to carry the matte information we'll need to set the drop down to RGB.

![](Pasted%20image%2020220815211229.png)

So now we're well on our way, but we still need to give the channels from the A pipe a new home built into this Checkerboard.

![](Pasted%20image%2020220815211254.png)

If we click the drop down menu we have a many options to choose from. But let's say the client has a specific need, and wants to calls this new channel: **`tiles`**. We'll need to create them. So let's click `new`

![](Pasted%20image%2020220815211355.png)

We can now create a new layer that will be built into our final output. Since the client wanted to call it **`tiles`** that what we'll put.

But let's take it one step further and say the client wants each channel in the **`tiles`** to have a unique name! The Red Channel must be called `one`, Green must be called `two`, and Blue must be called `three`. Why? Because in this example our client wants it like that. So we roll with it.

![](Pasted%20image%2020220815211829.png)

So here we have it. A new layer called **`tiles`** with a `one`, `two`, and `three` channel. Click ok.

![](Pasted%20image%2020220815211943.png)

One step closer. Now we have a little fun and connect the dots.

![](Pasted%20image%2020220815212013.png)

So now the client has their checkerboard and decideds to tweak some of the colours in the DI session. They say something along the lines of "Make that part more green, and that part purple!" And because the colourist has the mattes built right in they can make the changes on the fly and look like a superstar!!

![](Pasted%20image%2020220815212343.png)

Notice how the Grade2 is using the `tiles.three` as the mask!

And that's the basics on shuffling extra layers and channels with the New Shuffle Node.

---

**Bonus tip**

The new Shuffle node also makes it VERY easy to take channels from your A pipe and plug them right into the the original output. 

So now your alpha is carrying the matte from your Red Channel from the A pipe!

![](Pasted%20image%2020220815212513.png)

Now that's handy!!
