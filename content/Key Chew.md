---
title: Key Chew
draft: false
tags:
---
# Key Chew

One of my favourite tools ever!

![[Pasted image 20240508212542.png]]

I'm not the biggest fan of Nuke's default Eroder, (although the [Dilate Erode](https://publish.obsidian.md/vfx/Dilate+Erode) does have some amazing uses) and through my years I've come across this Key Chew, which supposedly mimics the old Shake KeyChew.

Copy and paste the following code directly into Nuke and enjoy!

```
set cut_paste_input [stack 0]
version 14.1 v2
push $cut_paste_input
Group {
 name KeyChew
 selected true
 xpos -597
 ypos 159
 addUserKnob {20 KeyChew}
 addUserKnob {7 chew R -100 100}
 addUserKnob {7 soften R 0 50}
 addUserKnob {6 matteMult +STARTLINE}
}
 Input {
  inputs 0
  name Input1
  selected true
  xpos -16
  ypos -192
 }
 Dot {
  name Dot1
  xpos 18
  ypos -90
 }
set N33463e00 [stack 0]
 Dot {
  name Dot2
  xpos 155
  ypos -61
 }
push $N33463e00
 Invert {
  channels alpha
  name Invert1
  xpos 55
  ypos -42
 }
push $N33463e00
 Switch {
  inputs 2
  which {{chew>=0?0:1 i}}
  name Switch1
  xpos -16
  ypos 25
 }
 Blur {
  channels alpha
  size {{abs(chew) i}}
  name Blur1
  xpos -16
  ypos 53
 }
 Multiply {
  channels alpha
  value {{max(Blur1.size*1.5,1) i}}
  name Multiply1
  xpos -16
  ypos 95
 }
 Clamp {
  channels alpha
  minimum_enable false
  name Clamp1
  xpos -16
  ypos 137
 }
 Gamma {
  channels alpha
  value {{relationCurve(abs(chew)) i}}
  name Gamma1
  xpos -16
  ypos 179
  addUserKnob {20 User}
  addUserKnob {7 relationCurve}
  relationCurve {{curve l 1 x5 0.95 0.8 x20 0.5 x40 0.3 x80 0.2 x200 0.1}}
 }
set N159d8000 [stack 0]
 Merge2 {
  inputs 2
  operation minus
  Achannels alpha
  Bchannels alpha
  output alpha
  name Merge1
  xpos 121
  ypos 235
 }
 Clamp {
  channels alpha
  maximum_enable false
  name Clamp2
  xpos 121
  ypos 277
 }
push $N159d8000
 Switch {
  inputs 2
  which {{chew>=0?0:1 i}}
  name Switch2
  xpos -16
  ypos 340
 }
 Blur {
  channels alpha
  size {{soften i}}
  name Blur2
  xpos -16
  ypos 368
 }
set N330bf400 [stack 0]
 Premult {
  name Premult1
  xpos 53
  ypos 426
 }
push $N330bf400
 Switch {
  inputs 2
  which {{matteMult i}}
  name Switch3
  xpos -16
  ypos 469
 }
 Output {
  name Output1
  xpos -16
  ypos 536
 }
end_group
```