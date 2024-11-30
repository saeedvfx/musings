---
title: ST Map Transforms
draft: false
tags:
---
Let's have some fun with STmaps!

Remember how we were able to use it to do [basic transforms](STmaps)?

Let's use a keymix and transform part of the STmap?


![[Pasted image 20220806111034.jpeg]]


As you can see from my STmap, in the expression node, I rotated it and scaled it a little larger. Then using a roto shape and a keymix, I mixed the results and now have a blob-like shape of my transformed image right smack in the middle of my original STMap.

![[Pasted image 20220806111239.jpeg]]

Hey that's kinda cool. But why go through all the trouble of using an STmap for something you can do directly?

Let's add a blur to that roto shap we created...

![[Pasted image 20220806111643.jpeg]]

Give it a value of 50 for this example and viola!
Things start to get funky!

![[Pasted image 20220806111805.jpeg]]

The STmap underneath has softened it's edges along the roto and now the pixels are getting smooshed around and creating an interesting result.

![[Pasted image 20220806111905.jpeg]]

Let's take it one step further and reduce the opacity of the keymix to 50% and reveal half the original STmap.

![[Pasted image 20220806112040.jpeg]]

Our warped checkerboard has gone "halfway back" to it's original position. Why? Because we are now reveal a combination of half the original pixels and half the newly transformed pixels on the STmap. 

Now imagine what you could do if you ANIMATED that keymix?