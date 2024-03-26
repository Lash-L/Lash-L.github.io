---
title: Troubleshooting
layout: page
nav_order: 8
description: "How to troubleshoot your printer"
permalink: /ender3_v2_neo/troubleshooting
---

## Help! I am having a physical issue with my printer (it is saying the temp is too high or low or it is acting strangely)

The first thing to check in situations like this is that your printer is on the right Voltage setting for your home. Check the switch on the back to make sure it is correct.

The second thing to check is that if you have something plugged in to the microusb port on the printer, you want to make sure it is not outputting any power. Remove the cable and see if you still have any issues. If you do, you need to cover the 5V pin on the usb cable.

## Help! I updated firmware and now my screen is not working!

Sometimes when you update firmware, you also need to update the firmware on your screen as well.
1. Figure out what kind of screen you have: [How do I know what screen I have?](https://lash-l.github.io/ender3_v2_neo/firmware_update#step-two-install-the-firmware)
2. Format a microsd card to FAT32 with 4096Bytes for allocation size
3. If you have a DWIN screen download [this](https://downgit.github.io/#/home?url=https://github.com/mriscoc/Ender3V2S1/tree/Ender3V2S1-Released/display%20assets/stock/DWIN_SET), If you have a DACAI Screen -download [this](https://downgit.github.io/#/home?url=https://github.com/mriscoc/Ender3V2S1/tree/Ender3V2S1-Released/display%20assets/stock/private)
4. Download the official Creality Firmware [here](https://www.creality.com/pages/download-ender-3-v2-neo) - This part could be optional, but I have heard of people having issues if they don't have this.
5. Take the firmware.zlib from the official creality firmware and the DWIN_SET folder or the private folder and put them both on the microsd
6. Unplug the printer, put the microsd card in the microsd slot ON THE BACK OF THE DISPLAY!!! If you put it in the regular sd reader, it will not fix your problem.
7. Plug in the printer, let the screen start up, it will say it is installing everything, and then once it finishes and it gets to a black screen with ??? or something similar on it, turn the printer off and remove the microsd card

## I failed updating my firmware and now every time I try to install it again nothing happens.
Once a firmware.bin is used once, it can't be used again. You have to change the name, i.e. add a 2 before the .bin.

`firmware-20230106-003853.bin` becomes `firmware-20230106-003853_2.bin`