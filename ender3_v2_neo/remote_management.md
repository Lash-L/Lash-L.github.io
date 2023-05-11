---
title: Remote Management
layout: page
nav_order: 6
description: "How to setup remote management for your printer."
permalink: /ender3_v2_neo/remote_management
---
This page is still a WIP

Remote Management allows you to 
1. Keep track of your printer progress without being next to it
2. Start, pause, or stop a print remotely
3. Setup a camera to check on your print.
4. Run terminal commands on the printer
5. Manually control your printer

The most popular remote management tool is Octoprint, that is what I use, so that is what I will walk you through.
## Requirements:
* A Device to run Octoprint on (I use a Raspberry pi, but those are hard to come by right now (use [rpilocator](https://rpilocator.com/?instock) to try to find one) Use the Raspberry Pi 3B, 3B+, 4B, or Zero 2, I would recommend with a minimum of 2GB of ram, I would probably go up to 4GB if you can. Or you can buy a [Renewed NUC](https://www.amazon.com/s?k=NUC&i=electronics&rh=n%3A172282%2Cp_n_condition-type%3A16907720011%2Cp_36%3A5000-&s=price-asc-rank&dc=&crid=35010B85E75IL&qid=1674744785&rnid=386442011&sa-no-redirect=1&sprefix=nuc%2Caps%2C120&linkCode=ll2&tag=ender3v2neotutorial-20&linkId=ebf191ffde424f0587d47a0091571e65&language=en_US&ref_=as_li_ss_tl) - these are becoming increasingly popular with the self-hosted community because they are much more powerful than raspberry pis, they are available, and they aren't much more money. They do however use more energy.
* If using a Raspberry pi:
  * Something to use for storage:
    * Microsd cards work, but do go bad faster than normal and you have end up having to reinstall. but if you do go with a microsd (cheapest option), I would get a nicer microsd such as [Samsung High endurance](https://www.amazon.com/dp/B09WB35BXS?th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=84d6779b67255fa3a0c356dea0d0c106&language=en_US&ref_=as_li_ss_tl)
    * M.2 ssd - to run this you need an [enclosure](https://www.amazon.com/SSK-Aluminum-Enclosure-Adapter-External/dp/B07MNFH1PX?crid=3TAA0CEJED0ZE&keywords=m.2+ssd+enclosure&qid=1672874105&s=electronics&sprefix=m.2+ssd+enclosure%2Celectronics%2C87&sr=1-6&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=65411a6ba6c70f1845f0251c23507c82&language=en_US&ref_=as_li_ss_tl) I found this cheap one on amazon, you will be limited by usb anyways so you don't need anything super high speed. And then you need a [m.2 ssd](https://www.amazon.com/Western-Digital-500GB-SN570-Internal/dp/B09HKGGPLR?crid=3FG7LXDXHRC9X&keywords=m2.%2Bssd&qid=1672874212&s=electronics&sprefix=m2.%2Bssd%2Celectronics%2C100&sr=1-2-spons&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUExUldXR0Y0VllVNjlUJmVuY3J5cHRlZElkPUEwNTQyNzQyMU1ZT1JBQk9IU01UVSZlbmNyeXB0ZWRBZElkPUEwMzkyNjk4MUZPUk1QV1gyRTBJMyZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=5b8316fcf41ac4a0cbd4f9e8b1731d4d&language=en_US&ref_=as_li_ss_tl) If you plan to run other things on the pi, you may want to increase the size.
  * Power Adapter - Again use a high quality one or you will end up regretting it. For the rpi4 use [Canakit 3.5A usb-c](https://www.amazon.com/CanaKit-Raspberry-Power-Supply-USB-C/dp/B07TYQRXTK?crid=1FAEQ99TKNJ8B&keywords=cana+raspberry+pi+4+power+adapter&qid=1672873874&s=electronics&sprefix=cana+raspberry+pi+4+power+adapte%2Celectronics%2C99&sr=1-3&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=2b5fdd825af20b218aa4cbbf670bf912&language=en_US&ref_=as_li_ss_tl) for the rpi3 use [Canakit 5A micro-usb](https://www.amazon.com/CanaKit-Raspberry-Supply-Adapter-Listed/dp/B00MARDJZ4?crid=1FAEQ99TKNJ8B&keywords=cana+raspberry+pi+4+power+adapter&qid=1672873874&s=electronics&sprefix=cana+raspberry+pi+4+power+adapte%2Celectronics%2C99&sr=1-4&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=a0ada17aa56ebb31fc18792325cd49fe&language=en_US&ref_=as_li_ss_tl)
  * (Optional) [A Camera](https://www.amazon.com/dp/B07SN8HB1R?th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=9c9967e58b709bd4e42bcf34f9ba78ca&language=en_US&ref_=as_li_ss_tl) - The quality on this camera isn't too high, for checking up on your print it should be fine, but if you want to make a cool timelapse or use any of the fancy octoprint ai to detect if the print failed, you may want to step up in quality. (you can also use a regular webcam)
* (Optional) If you aren't running a raspberry pi, you need a [Webcam](https://www.amazon.com/s?k=webcam&i=electronics&rh=n%3A172282%2Cp_36%3A1253503011&dc=&ds=v1%3AKvTPbgN%2FN%2FLEumjCHCqlcUYNt61kxIBFN%2Bt84qert%2B8&crid=1NKIIYS4P68ZE&qid=1672874504&rnid=386442011&sa-no-redirect=1&sprefix=webcam%2Celectronics%2C105&linkCode=ll2&tag=ender3v2neotutorial-20&linkId=eb2c4627026f26e272c98f1bbd6dcb51&language=en_US&ref_=as_li_ss_tl) if you want to be able to watch it print, any old webcam will do just try to find one that will fit a camera holder stl that someone has already made.
* A High quality Data micro-usb cable with ferrite. I recommend this [Monoprice one](https://www.amazon.com/Monoprice-3-Feet-Micro-24AWG-Ferrite/dp/B004C4WEVI?crid=2PJ8WM6BXC9GB&keywords=micro%2Busb%2Bferrite%2Bcable&qid=1672874569&s=electronics&sprefix=micro%2Busb%2Bferrite%2Bcabl%2Celectronics%2C97&sr=1-3&th=1&sa-no-redirect=1&linkCode=ll1&tag=ender3v2neotutorial-20&linkId=cf6b0bdef7903559f8b50c84557c2e7c&language=en_US&ref_=as_li_ss_tl) Pick what color and length you want

## How to install
There are three installation methods:
### OctoPi
If you are using a raspberry pi, you can use [Octopi](https://github.com/guysoft/OctoPi), Typically I am against specialized OS's on devices like this, because it limits your ability to run other services at the same time. BUT if you plan to use a camera with a raspberry pi, this is the easiest way to go.
1. Install [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
2. Enter your microsd into your pc
3. Launch RPI imager
4. Operating System -> Other Specific Purpose OS -> 3d Printing -> Octopi
4. Select the microsd as the storage
5. Configure: allow ssh, setup wifi (Unless you are using ethernet), and create a username and a password.
6. Write

### Docker
1. [Install Docker (Steps for Ubuntu)](https://docs.docker.com/engine/install/ubuntu/)
2. Once docker is installed


### Standalone Instructions copied from [here](https://community.octoprint.org/t/setting-up-octoprint-on-a-raspberry-pi-running-raspberry-pi-os-debian/2337)
1. Make sure you have python installed (most linux downloads come with it)
2. Run the following commands

~~~
cd ~
sudo apt update
sudo apt install python3 python3-pip python3-dev python3-setuptools python3-venv git libyaml-dev build-essential libffi-dev libssl-dev
mkdir OctoPrint && cd OctoPrint
python3 -m venv venv
source venv/bin/activate
~~~

~~~
pip install pip --upgrade
pip install octoprint
~~~

You may need to run 

~~~
sudo usermod -a -G tty (account-name)
sudo usermod -a -G dialout (account-name)
~~~

~~~
wget https://github.com/OctoPrint/OctoPrint/raw/master/scripts/octoprint.service && sudo mv octoprint.service /etc/systemd/system/octoprint.service
~~~

Adjust the paths to your octoprint binary in /etc/systemd/system/octoprint.service. 
you can do this by running `sudo nano /etc/systemd/system/octoprint.service` Then you should change the username to your username, and then in the path change pi to your username. This script assumes the default username is pi which is no longer allowed by raspberry pi.

Then add the script to autostart using `sudo systemctl enable octoprint.service`.

This will also allow you to start/stop/restart the OctoPrint daemon via

`sudo service octoprint {start|stop|restart}`

Go ahead and start octoprint. access it by going to http://ip-address-of-device:5000 if you don't know the ip address you can get it by running ifconfig in the terminal.

## How to set it up
Now that you have it installed there are a few things you should do.
1. That the Usb end of the usb to micro-usb cable, get it so that the pins inside are facing upward and you can see them. grab some electrical tape, cut it and then using tweezers or anything that will allow you to reach far in, cover the last( far-right) pin with electrical tape. Basically the usb cable will send power to the printer and it will cause you all kinds of issues. By covering that pin, you stop the flow of power to the printer. I originally skipped this step and it caused me issues with my prints failing. you can test this works by plugging the usb into your device, and then plugging the micro-usb into the printer. Then turn off and unplug the printer. If the screen stays on, then power is still coming through the usb and you did not cover it correctly.