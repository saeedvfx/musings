---
title: Luminance
draft: false
tags:
---


Luminance is the MEASURABLE brightness of an image. 

Checking your pixels values of an image, the brighter something appears the higher the pixel values, and in turn, the darker something is the lower the pixel values. 

Finding the Luminance is a simple formula:
$$
L = .3R + .59G + .11B
$$
In plain English: 
- 30% of the **<font style="color:red">RED</font>** channel 
- 59% of the **<font style="color:green">GREEN</font>** channel 
- 11% of your **<font style="color:blue">BLUE</font>** channel
Equals the **Luminance** (100%)

Let's try the math on the image below.

![[Pasted image 20220823195021.jpeg]]

The Luminosity of the area is `0.127` with an RGB of ( .129 , .126 , .139)

$$ 
.3*(.129) + .59*(.126) + .11*(.139)
$$
$$ 0.0387 + 0.07434 + 0.01529 = 0.12833
$$

Which is close to the Luminance Value displayed of `0.012778`.
The actual Math Nuke is using is probably slightly different, but it's close enough to get an idea.

> [!tip] 
You can use this value to help you [balance your colours across shots](Colour_Balance)
