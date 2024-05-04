
## Did you know there is a Ghost in your Grain?

Let me show you.

---

We'll use a frame from the Blender Open Source short film, [Tears of Steel](https://mango.blender.org/)

![[Pasted image 20221227205051.jpeg]]
Frame 1853 downloaded from [here](https://media.xiph.org/tearsofsteel/tearsofsteel-footage-exr/04_5f/linear_hd/)

---

Here is a closeup image of the blue channel.

![[Pasted image 20230107150343.jpeg]]


Here is the same image denoised using [[Neat Video]].

![[Pasted image 20230107150424.jpeg]]


We can now separate the grain from the original plate as follow...

![[Pasted image 20230107150711.jpeg]]


Which gives us the following results (exposed up in order to see the results better).

![[Pasted image 20230107150807.jpeg]]

It's the grain, but with the dude's texture built right in! 

You can take any footage, subtract the denoised version of it, and you'll get a grain pattern with a "ghost" of what was filmed.

Why is this important to know?

Well... let's plus it back on top

![[Pasted image 20230107151407.jpeg]]

![[Pasted image 20230107150343.jpeg]]

And we're right back at where we started!

So in theory you could use the separated grain and plus it back on top when your comp is done. 

Why do I say "in theory"? Let's say we needed to push in at some point in the comp, so the footage is a little different from where we started.

For this example I'll push in 10%

![[Pasted image 20230107151715.jpeg]]

Let's take a look at the results.

![[Pasted image 20230107151742.jpeg]]

We've brought the grain back, but it's from the original sized grain, so we're getting some artifacting here.

Let's compare the original plate to our scaled up comp:

![[Pasted image 20230107151857.jpeg]]

The image on top is the scaled up version. Below is the original version. The artifacting we are seeing is the ghost grain of the green channel messing up the look of the hair along the right edge.

Let's take this a step further and **mirror** the image and see what happens. 

![[Pasted image 20230107152028.jpeg]]

Wow... that's some nasty ghosting. 

Taking a look at the original grain we can see what is causing all that. You can even clearly see the arms from the desk lamp in the lower left portion.

![[Pasted image 20230107152137.jpeg]]

So while plus the original grain back on top is great way to regrain your footage, you need to be mindful of the ***Ghost in the Grain***.

![[Pasted image 20230107152900.jpeg|300]]


