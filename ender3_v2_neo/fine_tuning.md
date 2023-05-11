NOTE: If you are reading this page I assume you have flashed Marlin onto your printer. 

If you are looking for more fine tuning, I would recommend the [Eliis3dp guide](https://ellis3dp.com/Print-Tuning-Guide/)

## Use Chep's Profiles
A guy much smarter than me created various profiles that do a lot of optimization for cura printer profiles for the Ender 3 (and they work for the 3v2 as well).

[His video is here](https://www.youtube.com/watch?v=jM_jdsx5yFc&t=165s&ab_channel=CHEP)

These are his profiles: Download them all

[Best (0.12)](https://social.thangs.com/m/184722)

[Good (0.20)](https://social.thangs.com/m/184723)

[Extra Fast (0.28)](https://social.thangs.com/m/186289)

[Hyper Fast (0.32)](https://social.thangs.com/m/186263)

Once you have downloaded them, create a new machine profile settings in cura, then open each .3mf file one at a time in cura. It will add each profile. Then you can delete the machine profiles it created, and rename each profile. Use these instead of the default profiles. you will see a speed-up and better quality.


## Tramming your bed:
1. Go to Prepare-> Bed Tramming -> Tramming Wizard
2. Let it probe the 4 corners, pay attention to the values as they show up as it will eventually normalize them and in my opinion it is better to zero them all out rather than to make them all equal. (i.e. all corners being .3 is just as good as all being 0.0 in the eyes of the firmware)
3. If the corner is a positive decimal, lower that corner, if the corner is a negative decimal, raise that corner. It will also tell you what to do once the tramming is done if that is easier for you.

## Probe Z-Offset
1. Auto-Home
2. Move z to 0.0
3. Prepare->Z-Probe Wizard -> Probe z-Offset
4. Use the typical paper test (lower the z-offset until a piece of paper is just barely getting caught by the nozzle (this can range a lot depending on the level of your bed and how the probe was installed on your machine in the factory.) I have seen values as low as 1.something and as high as 3.something.
6. Tram the bed again

## Auto-Mesh Leveling
1.Set Advance -> Mesh Leveling -> Mesh Points to the resolution you would like (the higher the resolution the better the leveling and bed adhesion, but the longer it takes). I personally do 7x7 for any print I care about and 4x4 for any print I need quicker.
2. Hit Mesh Inset and then Maximize Area and then Center Area.
3. Return home, go to Advance and then hit store settings.

## Slicer Settings
I have my slicer set to automatically run the Mesh leveling before every print and I would really recommend this. It is possible to just use the saved mesh, and if that is something people are interested in, I can add it to the tutorial
Start G-code (Bi-linear mesh):
~~~
M201 X500.00 Y500.00 Z100.00 E5000.00 ;Setup machine max acceleration
M203 X500.00 Y500.00 Z20.00 E50.00 ;Setup machine max feedrate
M204 P500.00 R1000.00 T500.00 ;Setup Print/Retract/Travel acceleration
M205 X8.00 Y8.00 Z0.40 E5.00 ;Setup Jerk
M220 S100 ;Reset Feedrate
M221 S100 ;Reset Flowrate
G92 E0 ; Reset Extruder
G28 ; home all
G29 ; Run mesh leveling on every print
C108 ; Close the mesh viewer (optional)
G29 F 10.0 ; set fade height to 10mm
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X0.1 Y20 Z0.3 F5000.0 ; Move to start position
G1 X0.1 Y200.0 Z0.3 F1500.0 E15 ; Draw the first line
G1 X0.4 Y200.0 Z0.3 F5000.0 ; Move to side a little
G1 X0.4 Y20 Z0.3 F1500.0 E30 ; Draw the second line
G92 E0 ; Reset Extruder
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X5 Y20 Z0.3 F5000.0 ; Move over to prevent blob squish
~~~
Start G-Code (UBL)
M201 X500.00 Y500.00 Z100.00 E5000.00 ;Setup machine max acceleration
M203 X500.00 Y500.00 Z20.00 E50.00 ;Setup machine max feedrate
M204 P500.00 R1000.00 T500.00 ;Setup Print/Retract/Travel acceleration
M205 X8.00 Y8.00 Z0.40 E5.00 ;Setup Jerk
M220 S100 ;Reset Feedrate
M221 S100 ;Reset Flowrate
G92 E0 ; Reset Extruder
G28 ; home all
G29 L0 ; Load mesh from slot 0 (or use any other previously saved slot)
G29 A ; Activate UBL
G29 J ; Auto tilt mesh (optional)
G29 F 10.0 ; set fade height to 10mm
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X0.1 Y20 Z0.3 F5000.0 ; Move to start position
G1 X0.1 Y200.0 Z0.3 F1500.0 E15 ; Draw the first line
G1 X0.4 Y200.0 Z0.3 F5000.0 ; Move to side a little
G1 X0.4 Y20 Z0.3 F1500.0 E30 ; Draw the second line
G92 E0 ; Reset Extruder
G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
G1 X5 Y20 Z0.3 F5000.0 ; Move over to prevent blob squish
End G-Code:
~~~
G1 X0 Y220 ;Present print
M106 S0 ;Turn-off fan
M104 S0 ;Turn-off hotend
M140 S0 ;Turn-off bed
M84 X Y E ;Disable all steppers but Z
~~~

## Extruder Settings
This is something that is frequently overlooked but once configured will make a impact on your prints. It makes sure the correct amount of fillament is extruded.

[This is the guide I learned from](https://ellis3dp.com/Print-Tuning-Guide/articles/extruder_calibration.html) I would recommend doing things slightly differently for the ender 3 v2 neo

To be able to do this you need to have terminal access to your printer. You can do this by plugging in a computer with a micro-usb cable and installing software like Pronterface or setting up a remote-management tool like Octoprint. If you have any desire to be able to print to your printer without having to remove the microsd card, upload g code onto the sd card and then put it back in your printer. I would recommend setting up Octoprint - [which I have a guide on here.](https://github.com/conway220/Ender-3-V2-Neo-Setup/wiki/Remote-Management-(Octoprint))

### Steps
1. Retract all of your filament until it is just barely going through the hole after the gears, it should still slightly be in the bowden tubing.
2. Remove the Bowden tube from the start of the Bowden tube(not where it connects to the extruder) You just remove the blue tab, and then the tube is able to be pulled out. (Now would be a great time to replace the bowden tubing if you plan to do that, I have a guide for that here.)
3. Preheat your printer. (This is only to get past safety settings where it wont let you extruder while cold.)
4. Cut the filament as flush as you can with the hole where the bowden tubing originally connected. (This is the method I did as it was easier and gave me better success, but you can also measure the distance before it goes into the gearbox, you can see that method on the link I linked above)
5. Run the following Gcode in the terminal to make sure there are no issues extruding.
`M83 ; E relative`
`G1 E4 F60 ; Extrude 4mm at 1mm/s (60mm/min)`
6. As long as everything goes right, cut the filament flush again and then run the following in the terminal:
`M83 ; E relative`
`G1 E100 F60 ; Extrude 100mm at 1mm/s (60mm/min)`
7. Cut the filament as flush as you can again like you did before. Straighten the filament as much as you can and measure it. 
8. Run `M503` in the terminal. Then look for a line that says echo: M92 then has a Z Y and Z value then a E value. My original # value was 93, and if you flashed with my configuration yours should be as well. If someone who didn't flash could tell me what the default value was, that would be great.
9. Take that E value and multiply it by (100/(length of filament you cut). So if your E value was 93, and you had 95mm of filament extrude when you ran the above command, you should do 93 * (100/95) resulting in a new E-value of 97.8. This value will vary from person to person.
10.  Save the new Value by running the following in the terminal:
`M92 E(NEW E-STEP VALUE)` i.e. M92 E97.8
11. Repeat until when you run #6 you get 100mm out 2 times in a row. There will probably be some fine-tuning.
12. Save the value to the machine by running `M500` in the terminal.