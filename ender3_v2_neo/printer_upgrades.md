---
title: Printer Upgrade
layout: page
nav_order: 4
description: "What upgrades I recommend for your printer"
permalink: /ender3_v2_neo/upgrades
---

If you are looking for more upgrades, I'd recommend looking at [malachus' post on reddit](https://www.reddit.com/r/Ender3V2NEO/comments/zaxivx/creality_ender_3_v2_neo_modification_and_upgrade/). He does a great job of keeping it up to date.

NOTE: I am not an electrician, I am just a guy who does this for a hobby, as always take the needed precautions while working with electricity.


# Table of Contents
* [Silicone Spacers]
* [Bowden Extruder](upgrades#bowden-extruder-tubing--5-minutes)
* [Hotend fan](upgrades#hot-end-30-minutes)
* [Silent PSU fan](upgrades#silent-psu-fan-30-minutes)

# About these upgrades

These are upgrades I figured out how to do through various tutorials, googling, and troubleshooting. All of the tools I recommend are the ones that I use, I would not feel comfortable recommending anything else.

# Silicone Spacers (5 minutes)
## Why?
Springs are not consistent, if you find yourself have to relevel your machine frequently, this is a great addon. Since I installed mine I have rarely had to do a relevel.

## Supplies
* [Silicone Spacers](https://amzn.to/3vu3nbi)

## Steps
1. Unscrew all 4 leveling knobs until they come off
2. Lift your bed plate up and remove the springs
3. add the spacers
4. Screw back on!

# Bowden Extruder Tubing ( 5 minutes)
## Why?
The bowden tubing that comes with the ender heats up as it is installed going all the way against the nozzle. It will lose lubrication and PLA will get stuck or you will have other issues. This is a well document issue in ender 3s.

Here is my tubing from only using the printer for a few weeks, it's not too bad, but you can see how it would start to be problematic

![My Tubing](https://github.com/conway220/Ender-3-V2-Neo-Setup/blob/main/Upgrades/Bowden_Tubing/bowden_tubing.jpg?raw=true)

You can also replace to an all metal hotend, and CHEP did a video on this, but I liked the solution better, as it should also help filament go through a bit better and it was cheaper.

## Supplies
* [Capricorn Bowden Tubin](https://www.amazon.com/gp/product/B08G8MGLBX?ie=UTF8&psc=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=f32461208af7dd4380c1a80118b1d9d6&language=en_US&ref_=as_li_ss_tl)
* Wrench that came with Ender/ plyers
* smallish flathead screwdriver
* [Wire strippers](https://www.amazon.com/Klein-Tools-Cutter-Stripper-Stranded/dp/B00080DPNQ?crid=316Y441M10DW2&keywords=wire%2Bstrippers&qid=1673564002&s=hi&sprefix=wire%2Bstrippers%2Ctools%2C101&sr=1-6&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=b4e1f93676a675f8fd0af04916e2e6ec&language=en_US&ref_=as_li_ss_tl)
* Maybe zip ties depending on your own opinion

## Steps
1. Heat up your printer and remove your filament (You can use the unload filament functionality if you have flashed to marlin
2. Remove the blue plastic clips on either side of the bowden tube.
3. Remove the extruder cover (Keep in mind your nozzle will still be very hot). To remove the cover, there is one screw behind the cover, and then two tabs on the left side of the extruder (looking from behind) and one tab on the right side of the extruder. Use a flathead screw driver to push those carefully away from the backing.
4. Push down on the plastic bit that is sticking out where the bowden tube connects, you should then be able to pull out the tube. You can start on either side. Do both sides and slide the tube out from under the zip ties. (You may have better luck for the one on the extruder side to start step 5 partially first. aka losen the connector)
5. Using a wrench/ plyers, grab the bowden connector that connects to the heatsink and remove it. 
6. Replace with one of the ones that has the biggest threads in the kit. 
7. Tighten it all the way you can with your hand, then slide the tubing in (push down on plastic tab while you do so), do this until it can't go anymore, you should have pushed in enough to get to the nozzle. You could also potentially try putting the bowden tubing into the connector before you install the connector, put the tubing down as far as it should go, and then slide the connector down and screw it in to the heatsink. Once you have it all the way in you should tighten it with a wrench.
8. Slide the new tubing under the zip ties if you can, if you can't, you probably want to put new zip ties on.
9. Connect it to to non-extruder side
10. screw the extruder cover back on
11. Reload the filament.

# Hot end (30 minutes)

## Why?
The stock fan is rather loud and can be quite annoying in my opinion. Using an app on my phone, I got around 74db when I placed the phone up the part cooling fan. After this upgrade, I got around 55db

## Supplies
* 24v 40mm fan of depth 10mm,15mm, or 20mm
* 3D Printed shroud to match (10mm use stock), [15mm](https://www.thingiverse.com/thing:5783989), [20mm](https://www.thingiverse.com/thing:5748866)
* [(Optional) Fan grill](https://www.digikey.com/en/products/detail/ebm-papst-inc/LZ29-1/441857?s=N4IgTCBcDaICwAYC2SAEAzAhgO1QcwCcBLAGxJAF0BfIA)
* [Heat gun (Recommended)](https://www.amazon.com/dp/B09QRN12MW?coliid=I2OBVLCKNGAZ3G&colid=2ER3G7QXE7BQ3&psc=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=5b0be74cadd9003d52cdbd6ac8f395b9&language=en_US&ref_=as_li_ss_tl) or [Soldering Iron](https://www.amazon.com/dp/B000AS28UC?coliid=I3MQWKMHU2JKLQ&colid=2ER3G7QXE7BQ3&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=36958ea15c22a25b73f3434a7cae8306&language=en_US&ref_=as_li_ss_tl)
* (Recommended) [Solder seal wire connectors](https://www.amazon.com/dp/B07S62KYSL?th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=4c440f046b88411d682e7f038f5cb585&language=en_US&ref_=as_li_ss_tl)
* [Wire strippers](https://www.amazon.com/Klein-Tools-Cutter-Stripper-Stranded/dp/B00080DPNQ?crid=316Y441M10DW2&keywords=wire%2Bstrippers&qid=1673564002&s=hi&sprefix=wire%2Bstrippers%2Ctools%2C101&sr=1-6&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=126522e600625dd2441365997b643d93&language=en_US&ref_=as_li_ss_tl)
* 2-4 Screws to fit your fan, I personally went to ACE to find these, but you can find them elsewhere depending on the size of your fan.
* Zip-ties

## How do I pick a fan?

The best way I found was going to [digikey](https://www.digikey.com/en/products/filter/dc-brushless-fans-bldc/217?s=N4IgjCBcpgLFoDGUBmBDANgZwKYBoQB7KAbXAFZyAmADggF0CAHAFyhAGUWAnASwDsA5iAC%2BBWADYEIZJHTZ8RUiFgAGCQE5yNEIxCt2XPkNEEwGgMzTZ83AWKQyE2AHYaqkAQnkLVcp5ANFw0aHTMLGlhYfz0DSE4eAWExEG0Na1RMOyVHcCp8iylYtnijJNMQAFoqDMgeAFdFBzIYkRSa3PR%2BXS9pXgATdjBVKilmEoTjYQIWAE8mHHY0LGQ2oA) and sorting by lowest db. The stock fan is supposedly 6 something CFM. That basically says how much air it will blow. But that's just a rumor and as far as I know no one has gotten Creality to say what it is. Some have had luck with 4.4CFM, but for me I wanted to be safe rather than sorry, so I used a fan with a CFM of 7. But if I would have found one I liked in stock, I would have done 5.5CFM. Some people will use 12V fans and use a buck converter to use it instead of a 24V fan. You will probably get a quieter fan, but buck converters fail, and it is another step. I would personally recommend against it, but if that is something you want to do, you can find steps online.

Pick the lowest db rating that you are okay with price + cfm of. I would also search digikey for a 40mm fan cover

## Steps
1. Unplug the printer!!! You can cause a short if you do not.
2. Remove the hotend shroud (Make sure you have printed your new one if you need it.) You can do this by removing the one screw on the back of the hot-end assembly and then using a flathead screwdriver to carefully lift up the two tabs on the (hot-end's) left and the one tab on the other side.
3. Remove some zip ties so you can move the cable shielding up.
4. Stagger the cuts on the two fan wires. Cut one lower than the other. cut the inverse of that staggering on your fan wire
5. Strip the wires about 1/4th- 1/2 of an inch
6. slide the solder seal connector(if you used my kit, use the smallest size) over the red fan wire. Then make both ends of the red wire into a 'hook' and hook them together pushing tightly on them. Then slide the solder seal connector over the area where the two wires hook. The silver middle part that has the solder should be over the wires. 
7. Make sure you are facing the heatgun away from the rest of the printer, and use the heatgun until the solder in the middle melts and the shrink tubing catches on to the wire. I typically do shrink tubing then soldering.
8. Repeat for the other wire.
9. Screw the fan into the shroud with the label facing the heatsink.
10. Re-attach the shroud and turn the printer back on!
11. If you have a high pitched noise that goes in and out, it is probably an issue with the pwm frequency. You can enable `FAST_PWM_FAN` in configuration.adv and `#define FAST_PWM_FAN_FREQUENCY 31400` that helped me a little bit. 

# Silent PSU fan (30 minutes)
I don't have clear data for this one as I do for the part cooling fan unfortunately (if someone does this one, please tell me your results!), but the powersupply is a) poorly cooled and b) rather loud. I definitely noticed a difference replacing this fan even after replacing the part cooling fan as well.

## Supplies
* 24v fan (I got one of size 80x80x25, but any size will work as long as you can find a shroud
* As long as you got a fan that is larger than the original, you will need new [legs](https://www.thingiverse.com/thing:4603075)
* 3D Printed shroud to match [80x80x25](https://www.thingiverse.com/thing:4601320)
* [Heat gun (Recommended)](https://www.amazon.com/dp/B09QRN12MW?coliid=I2OBVLCKNGAZ3G&colid=2ER3G7QXE7BQ3&psc=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=5b0be74cadd9003d52cdbd6ac8f395b9&language=en_US&ref_=as_li_ss_tl) or [Soldering Iron](https://www.amazon.com/dp/B000AS28UC?coliid=I3MQWKMHU2JKLQ&colid=2ER3G7QXE7BQ3&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=36958ea15c22a25b73f3434a7cae8306&language=en_US&ref_=as_li_ss_tl)
* (Recommended) [Solder seal wire connectors](https://www.amazon.com/dp/B07S62KYSL?th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=4c440f046b88411d682e7f038f5cb585&language=en_US&ref_=as_li_ss_tl)
* [Wire strippers](https://www.amazon.com/Klein-Tools-Cutter-Stripper-Stranded/dp/B00080DPNQ?crid=316Y441M10DW2&keywords=wire%2Bstrippers&qid=1673564002&s=hi&sprefix=wire%2Bstrippers%2Ctools%2C101&sr=1-6&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=126522e600625dd2441365997b643d93&language=en_US&ref_=as_li_ss_tl)
* Phillips head screw driver

## How do I pick a fan?

The best way I found was going to digikey and mouser and sorting by lowest db. The stock fan has a CFM of 15 and a db of 22. You want to find anything higher or equal to 15 CFM and lower than 22 dba [(Source for original fan specs)](https://lash-l.github.io/ender3_v2_neo/printer_specifications#psu-fan). Personally, I ordered a backordered fan, and waited a few months to get a low dba/higher CFM.

 Some people will use 12V fans and use a buck converter to use it instead of a 24V fan. You will probably get a quieter fan, but buck converters fail, and it is another step. I would personally recommend against it, but if that is something you want to do, you can find steps online.

Pick the lowest db rating that you are okay with price + cfm of. I would also search digikey for a matching fan cover.

## Steps
1. Print the shroud + legs for the psu cover
2. Unplug the printer, leave the power switch on, and don't touch it for a few minutes(Let the capacitor drain)
3. Tilt the printer on its side (carefully). Prop it up making sure you aren't putting pressure on the z axis motor.
4. Remove the two screws on the bottom of the psu mount and the two screws on the top. You shouldbe able to slide it out.
5. Remove the allen screws on the top of the psu holder and the allen screw that is on the bottom closest to the power plug.
6. You can now take the bottom cover of the psu holder off and you should see the silver PSU.
7. Be careful with the cables while you are working on it, make sure you don't put too much stress on them.
8. There are four screws on the bottom of the sides of the psu, remove these and you should be able to take off that part. (You only need to do these four, all the other screws are holding other things in place)
9. Remove the existing fan from the psu cover
10. Cut the wires on both the existing fan and your new fan(Try to leave the same amount of space on both)
11. Strip the wires about an inch on both sides
11. For the red wires, Slide the solder seals connector(smallest size that will fit) on one side, then make both sides of the stripped wires into a hook. connect the two red wires with the hooks, then put pressure down and slightly twist. You want this to be secure. Then slide ths older seal connector over the wires so that the silver part is over the center of where the two wires meet. Use your heatgun to melt it until the solder is melted in the middle and the plastic is secure on the edges.
12. Do the same for the black cable
13. Secure the fan onto the new printer cover (make sure airflow is going the same way as the original!!) You can use the two screws that held down the original fan.
14. Repeat the previous steps in reverse to get it back on! You will have two extra pieces of metal that are no longer in user (the cover for the psu and the bottom of the psu mount)

# Silent Motherboard Cover
TODO

# Better- Bed Leveling Knobs
TODO

# Filament run-out sensor
TODO
[Official Creality Sensor](https://www.amazon.com/Official-Creality-Detection-Max%EF%BC%8CEnder-Motherboard/dp/B09NKWSZ31?crid=2HMZC3IAW45GU&keywords=filament+runout+sensor&qid=1672879762&s=industrial&sprefix=filament+runout+sensor%2Cindustrial%2C133&sr=1-4&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=d98866435bb4e62d890ec832cd811bdc&language=en_US&ref_=as_li_ss_tl)

# Remote Management
You can read my [octoprint guide here.](https://github.com/conway220/Ender-3-V2-Neo-Setup/wiki/Remote-Management-(Octoprint))