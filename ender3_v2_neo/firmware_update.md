---
title: Firmware Update
layout: page
nav_order: 2
description: "How and why to update your firmware"
permalink: /ender3_v2_neo/firmware_update
---

# Why should I update my firmware?
The default Creality Firmware does its job, but in terms of features, it just doesn't compare. Here are the big ones:
### Auto Bed tramming
The paper method of tramming your bed is okay, it obviously works as people are able to get great prints by using it. But with updated firmware, you can take the guess work out of it, no more "is the paper as tight in this corner as it is in that corner?". It probes each corner of the bed using CRTouch and gives you quantifiable numbers for each corner and directs you how to tram the bed. It will give you a decimal number for each corner a positive means it is too high and a negative means it is too low. It will give you the most effective move, i.e. "Lower bottom right" This is so much easier and more reliable than the paper method.
### Mesh leveling
This is the actual game changer. the firmware can probe a nxn square on the bed to create a map of the leveling/warping of your bed. It will then automatically adjust as needed to make sure you are always printing at the correct level. 
TODO: Add image

# Requirements
* [VS Code](https://code.visualstudio.com/)
* [PlatformIO Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide)
* [Latest Version of Marlin Professional Firmware designed for the Ender 3 v2 by Mriscoc (Download the source code)](https://github.com/mriscoc/Ender3V2S1/releases)
* [OEM Firmware for the Ender 3 V2 Neo](https://www.creality.com/pages/download-ender-3-v2-neo) - Should no longer be needed with newest version of mriscoc
* [My Configuration files for Marlin](https://github.com/conway220/Ender-3-V2-Neo-Setup/tree/main/Marlin_Configurations) You can technically use one of the defaults that comes with the firmware, but I would recommend using mine as I know for sure my changes work.
* [Know what board you have](https://lash-l.github.io/ender3_v2_neo/printer_parts#how-do-i-know-what-motherboard-version-i-have)
* A microSd card (The one that came with your printer will work fine)

# Installing the Firmware

## Step one: configuring Marlin
1. Open VS Code and open the Marlin firmware source code as a new project
2. In the /marlin/ folder replace the configuration.h, configuration_adv.h, and the version.h with my files.
3. Replace the platformio.ini in the root directory with my platformio.ini.
4. Change line 92 in configuration.h to whichever board version you have. I have both commented out. Delete the Generic V4 and replace with the V4.2.2 or V4.2.7 (They are commented in my example, but you can manually set them by adding 22 or 27 to the end of the V4). I don't know if this actual makes much of a difference as V4 is supposed to work for all 4.x, but I figure it is worth changing just in case
5. Look at the values of line 1491 in the configuration.h, My probe values are `NOZZLE_TO_PROBE_OFFSET { -37, -12.2, -1.47 } ` You should use a digital caliper to get your actual values, but these should be good enough for most people (Except the Z-Offset - which I would recommend fine tuning when you have installed the firmware.) Teaching Tech shows how to get these measurements [here](https://youtu.be/fN_ndWvXGBQ?t=177)
6. As long as PlatformIO was installed(You may need to restart VS Code if you haven't), and you opened the source code folder correctly. There should be a Check mark at the bottom of the VS Code page. Hit that and let the firmware compile.

## Step Two: Install the firmware
1. Format your microsd card to be FAT32 and have 4096 Bytes as the allocation unit size
2. Place the firmware-xxxx-x-x-x.bin that can be found in the .pio/build/STM32F103RC_creality/ folder (Note if you have already flashed your firmware before, you may need to change the .bin name)
3. Depending on your [https://github.com/mriscoc/Ender3V2S1/tree/Ender3V2S1-Released/display%20assets](Screen type) you should grab the private folder or the DWIN_SET folder from the display assets folder in the Marlin Source Code. Grab private if you have DACAI and grab DWIN_SET if you have DWIN. You can read more about this [here.](https://github.com/mriscoc/Ender3V2S1/tree/Ender3V2S1-Released/display%20assets) and put it on the sd card
4. Grab the firmware.zlib from the OEM firmware and put it on the sd card (this now seems to be included with mriscoc - so no need to grab from oem)
5. Turn off and unplug the printer
6. Place the microsd card in the front of the printer.
7. Plug the printer back in and turn it on
8. It will be black and eventually it will say Ender-3 V2 Neo Ready or something along those lines on the screen.
9. If you are missing icons or anything else on the display looks wrong, remove the microsd, turn the machine off and restart it. If that doesn't fix the problem, turn the machine off, remove the display screen, and then put the microsd card into the slot on the back of the display (you have to remove the allen screens on the back of the screen and take the back off). Turn the machine back on, The screen will go blue with orange text and eventually it will go to the creality logo that has question marks on it. Remove the microsd from the screen, reinstall the screen to the side of the machine, and then turn the machine on. You should now be good!
10. Follow [these](https://github.com/mriscoc/Ender3V2S1/wiki/How-to-generate-a-gcode-preview) steps to get g-code preview

Congrats! You have updated your firmware. I would recommend reading through my [fine-tuning your printer](https://lash-l.github.io/ender3_v2_neo/fine_tuning) page next to get the z-offset, meshing, and extruder steps correct.


# Upgrading to mriscoc 20230312

If you are reading this section, I assume you have already followed my guide once and you have the needed software to update the firmware.

## Step one: Configuring marlin
1. Write down any configurations you changed inside the menu, as those will be overridden when you update. (i.e. Z-offset)
2. Download the latest mriscoc from [here](https://github.com/mriscoc/Ender3V2S1/releases/tag/20230312)
3. Download my configuration from [here](https://github.com/Lash-L/Ender-3-V2-Neo-Setup/tree/main/Marlin_Configurations)
4. Make any changes you want to to my configuration file
Change line 92 in configuration.h to whichever board version you have. I have both commented out. Delete the Generic V4 and replace with the V4.2.2 or V4.2.7 (They are commented in my example, but you can manually set them by adding 22 or 27 to the end of the V4). I don't know if this actual makes much of a difference as V4 is supposed to work for all 4.x, but I figure it is worth changing just in case
5. Look at the values of line 1491 in the configuration.h, My probe values are `NOZZLE_TO_PROBE_OFFSET { -37, -12.2, -1.47 } ` You should use a digital caliper to get your actual values, but these should be good enough for most people (Except the Z-Offset - which I would recommend fine tuning when you have installed the firmware.) Teaching Tech shows how to get these measurements [here](https://youtu.be/fN_ndWvXGBQ?t=177)
6. Download the screen firmware from [here](https://github.com/mriscoc/Ender3V2S1/blob/Ender3V2S1-Released/display%20assets/dacai_update.zip?raw=true) - you probably don't need to do this - but it does not hurt. Previews worked for me without doing it. But I know not everyone has updated their screen firmware
7. Follow [these](https://github.com/mriscoc/Ender3V2S1/wiki/How-to-generate-a-gcode-preview) steps to get g-code preview

## Step two: Updating
Follow the steps [here](https://lash-l.github.io/ender3_v2_neo/firmware_update#step-two-install-the-firmware)