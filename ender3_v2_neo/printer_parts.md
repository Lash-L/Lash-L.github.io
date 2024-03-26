---
title: Printer parts
layout: page
nav_order: 7
description: "Learn what parts are in your printer."
permalink: /ender3_v2_neo/printer_parts
---
## How do I know what Motherboard Version I have?
If you look through the bottom of your printer, you should be able to see through the ventilation holes for the motherboard and see if it says 4.2.2 or 4.2.7 The text in the center is what matters.
### 4.2.2
![4.2.2 Board](https://github.com/conway220/Ender-3-V2-Neo-Setup/blob/main/Printer_Part_Images/Boards/4_2_2_board.png?raw=true)
### 4.2.7
![4.2.7 Board](https://github.com/conway220/Ender-3-V2-Neo-Setup/blob/main/Printer_Part_Images/Boards/4_2_7_board.jpg?raw=true)

## How do I know what Screen Version I have?
If you remove the screen from the side of the printer, and then remove the 4 screws holding the back on, you should see one of two screens:
### Dacai screen
![DACAI Screen](https://github.com/Lash-L/Ender-3-V2-Neo-Setup/blob/main/Printer_Part_Images/Screens/DACAI_display.jpg?raw=true)
### Dwin screen
![Dwin Screen](https://github.com/Lash-L/Ender-3-V2-Neo-Setup/blob/main/Printer_Part_Images/Screens/dwin_display.jpg?raw=true)

These Images for the screen are from [mriscoc's guide for flashing the screen](https://github.com/mriscoc/Ender3V2S1/tree/Ender3V2S1-Released/display%20assets), which you will view during the tutorial

## How do I know what Power supply fan I have?
The only way I am aware of to figure out what power supply fan you have is to remove the power supply. Once you remove the power supply, remove the small screws holding the top on (there is one under a sticker) (I will try to update this later to go into more detail.) Ender 3 v2's have a mix between 12v and 24v fans on the psu, but in my ender 3 v2 neo, I had a 24v fan. I have not heard of anyone having a 12v fan, but you should check as it is possible - if you end up finding a fan different than mine, please let me know and I will update this page. This is what my fan looked like

![PSU Fan](https://github.com/conway220/Ender-3-V2-Neo-Setup/blob/main/Printer_Part_Images/Fans/psu_fan_1.jpg?raw=true)

## How do I know what motherboard fan I have?
The only way I am aware of to figure out what motherboard fan you have is to remove the cover for the motherboard. First, there is a allen screw underneath the build plate. Remove that. Then remove the other three screws on the bottom of the device. The cover should then come off.
Again, as far as I am aware there are on 24v fans for the motherboard. But you should double check, and if you have a different fan then me, please let me know.

![Motherboard Fan](https://raw.githubusercontent.com/conway220/Ender-3-V2-Neo-Setup/main/Printer_Part_Images/Fans/motherboard_fan_1.webp)

## How do I know what stepper Drivers I have?
You need to open up your machine where the motherboard is, and look at the microsd card reader. there will be a handwritten letter or a sticker.
According to [this website:](https://printermods.co.uk/blogs/guides/creality-v4-2-2-v4-2-7-motherboard-stepper-driver-codes):

The code is 
~~~C = HR4988
E = A4988
A = TMC2208
B = TMC2209
H = TMC2225
T5 = TMC2225
T8 = TMC2208
~~~

You should probably have T8 as the neo should have the silent drivers.
