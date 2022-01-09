** NOTICE: ** Several people are still testing this. If you want something more stable, you may want to wait. You can see the [current testing status, known issues, workarounds, and faq's here](TESTING_STATUS.md).

[CHANGELOG](CHANGELOG.md)

## Disclaimer

The code within this repository comes with no guarantee; the use of this code is your responsibility.

I take NO responsibility and liability for how you choose to use any of the source code available here. By using any of the files available in this repository, you understand that you are AGREEING TO USE AT YOUR OWN RISK

# Marlin 2.x - Color UI - 3D Printer Firmware compiled for Elegoo Neptune 2

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

**Note:** The configurations and compiled versions are available in this bundle. 

This is a package of Marlin 2.x configurations for the Elegoo Neptune 2. The configurations are compatible with the Elegoo Neptune 2S. The source is a fork from [Marlin 2](https://github.com/MarlinFirmware/Marlin/releases). No changes have been made to the Marlin codebase, and only configuration files for the Elegoo Neptune 2 are added. 

These files are provided as opensource under the same [GPL v3](https://www.gnu.org/licenses/gpl-3.0) license as Marlin 2.

## Please Read and Consider:
I am providing these configurations to the community for free. If you find this helpful or your ETSY printer farm benefits from this (or makes you rich :grinning:), I would like you to please consider donating to a nonprofit close to my heart that supports my community. More information is at the end of this [README](#donation-request). 

# What are the features I get from using this?

All versions provided come with these features.

1. A safe version of alternative firmware.
   - I found a few configurations online and in repos that were not appropriately configured (Thermal runway protection was off or busted) 
1. An alternative UI
   - Not as "pretty," but much more helpful
   - Update many configuration values (including ESTEPS) right on the screen
   - PID Autotuning for the nozzle AND bed from the UI. 
1. [S-Curve Acceleration](https://github.com/synthetos/TinyG/wiki/Jerk-Controlled-Motion-Explained)
1. Adaptive Step Smoothing
1. ARC Support Enabled
1. **M600** Change filament at layer.
2. The screen will update if you are printing from Octoprint.

BLTouch versions also include:
1. Z Level Offset Wizard
1. **Live Z** Support
1. Bed tramming wizard option (I mean, you still need to level every once and a while)

# Do I lose any features if I use this?

The following items are not supported:

1. If you have a WIFI Card, it WILL NOT WORK (MKS made that call, not me) 
2. Power loss detection does not work. Same reason as above. 
3. Icon previews do not exist in UI

# Setup and install

## Getting things ready

NOTE: I recommend you use an sd card 8gb or less FAT Formatted for installing. Using anything larger has been an issue with some users. [If you do not have one this is the one I use (non-affiliate link)](https://amzn.to/3JIOzYL)

1. [Download the latest version here](https://github.com/just-trey/Marlin/releases/latest/download/Elegoo.zip).
2. Extract the zip file on your computer
3. Copy the desired `elegoo.bin` configuration to your SD Card. No other files are needed to install. 
   
   ***NOTE:*** **IT IS IMPORTANT YOU KNOW THE VERSION OF THE ZNP ROBIN NANO BOARD YOU HAVE, AND YOU NEED TO USE THAT VERSION OF THE FIRMWARE**
  
   - The directory structure is as follows: 
     
     ![dir structure](https://user-images.githubusercontent.com/10281380/148702987-9dd38cbb-fac2-4b16-aa44-5f9b72192f2a.jpg)

   - All firmware and configurations for 1.2 boards are in the 1.2 directory
   - All firmware and configurations for 1.3 boards are in the 1.3 directory
   - If you *DO NOT* have a BLOTUCH, use the file in the STOCK directory
   - If you *DO* have a BLOTUCH, use the file in the BLOTUCH directory
   - Neptune 2d version are avaiable with STOCK and BLOTUCH support following the same structre
## Install

1. Power off your printer
2. Put the sd card in with the appropriate `elegoo.bin` file... *Reminder: Did I mention to make sure you have the correct version for your board?*
3. Turn on your printer.
4. The firmware will install.
5. Once installed, click on the calibration touchpoints. When the touch calibration is complete, it will display a confirmation message. You may think it froze but give it a little time.

   Please note: After you click the bottom right calibration point, reboot your machine if it prompts you to click the top left again. I have never had to do this more than twice when installing the firmware. This may be a unique issue because I have had it since I bought this printer.

6.  Remove the SD Card from your machine
  
## (Optional, but recommended) PID AUTOTUNE your machine.

*Did you know?* - Elegoo ships with some default values for this, but they can vary with *every* machine. PID tuning is a safety feature, and unless you want my machine's values, I suggest you do this.

1. From the main screen click on *settings icon -> Configuration -> Advanced Settings -> NEXT ARROW (>) -> Tempeture -> PID AUTOTUNE E1*
2. The nozzle will heat up and down for a few minutes. When completed, the screen will display a confirmation message on the bottom of the status screen.
3. From the main screen click on *settings icon -> Configuration -> Advanced Settings -> NEXT ARROW (>) -> Tempeture -> NEXT ARROW (>) -> PID AUTOTUNE BED*
4. The bed will heat up and down for a few minutes. When completed, the screen will display a confirmation message on the bottom of the status screen.
5. From the main screen click on the *settings icon -> Configuration -> NEXT ARROW (>) -> Store settings*

## TIPS

### Z Offest Wizard Location

Located at: *settings icon -> Configuration -> Advanced Settings -> NEXT ARROW (>) -> Tempeture -> NEXT ARROW (>) -> Probe Offsets*

### BT Touch Probe offsets

You can modify the offset of you probe within the touch screen interface to center your nozzle. 
For example: If you happen to use [this dual fan printhead](https://www.thingiverse.com/thing:4949488), the X offset is 47.5
You can set this at: *settings icon -> Configuration -> Advanced Settings -> Probe Offsets*

### Live Z Offset (Baby Stepping) Location

While printing:  *settings icon -> Tune -> NEXT ARROW (>) -> Probe Z Offset*

# FAQ's

Q. Why only one file? What happened to the `elegoo.txt` file and the fonts and images?

A. Marlin 2 does not use any additional files for the provided configurations. If you were to compile using LVGL, you would also get an `assets` folder. 

Q. The touch screen does not seem very responsive. Especially at the bottom of the screen. What's up with that?

A. Yup. The color depth is also horrendous! So I choose very bright colors for the theme. If you know of a better quality compatible screen, I'd love to hear about it. I think a corner was cut on the machine to help keep costs down, which is very fair! A manual workaround is to use a stylus! I found one that works well and made a slide holder for it. 

Q: How do I know what version board I have?
A: There are two ways to identify what version board you have. 
  - Via the stock firmware interface:
    - From the main screen, click on * Settings -> About *
    - If the *Firmware* version is 1.x.x, you have a 1.2 board.
    - If the *Firmware* version is 2.x.x, you have a 1.3 board.
  - Visual confirmation (more effort, but if you are not running stock firmware, the only way): 	
  - Power off, unplug and remove the bottom plate cover from your machine (Note: One screw that attaches near the LCD is shorter than the rest. Be sure to put that screw back in the same place when you put it back together, or you can crack or put a dimple on the top of the case) 
  - The version number is printed directly on the board

    ![1-2board](https://user-images.githubusercontent.com/10281380/147952867-216f31e7-3df8-4679-9e6e-3f61c7d24c45.jpg)
    ![1-3board](https://user-images.githubusercontent.com/10281380/147952884-c4643537-1928-45d9-ae86-38522722a18b.jpg)

  
## Donation Request

Please consider donating to support the Tyler Wentz Memorial Fund if you find this helpful.

[![Donate](https://user-images.githubusercontent.com/10281380/147870647-23f016bf-29f9-41ec-a78f-81ef9633ff23.png))](https://golf.twentz.com/donations)

My son, Tyler Wentz, passed away after having a bodysurfing accident in 2015. We established a 501(c) (3) nonprofit organization to raise money to provide two scholarships in our community to deserving students. We are 100% volunteer-driven, and 100% of donations (less the 2.7% Square Processing Fee) will go straight towards supporting the scholarships. 

You can learn more about the Tyler Wentz Memorial Fund fund at: https://twentz.com/ 


---

## Possible TODO's (PR's accepted)

1. Provide a configuration with linear advance on
2. Automate configuration building

---

Have fun clicking around the interface. Let me know if you have any issues, and Happy Printing!
