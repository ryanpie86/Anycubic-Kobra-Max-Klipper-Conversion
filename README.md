# Anycubic-Kobra-Max-Klipper-Conversion

**You will need to remove resistor R66 on your circuit board and place it in R65 spot.**
**Please see https://www.reddit.com/r/anycubic/comments/ynvbj0/anycubic_kobra_working_config for detailed information**

The printer this has been configured for is stock minus just some Capricorn tubing (and of course the Klipper conversion)

I have tried to credit everyone for the information I have gathered in the printer.cfg. If you feel I have missed something, please do say so.

Also uploaded is a Cura project file containing my optimized 0.2 PLA+ slicer profile, and of course a Cali Cat sitting in it. Import the project into Cura as a new profile.

Oh, and no, your screen will not work after this. After you flash and get the 4 beeps the screen will freeze. Wait a few seconds, power the machine off, and then disconnect the screen. You won't be needing that where you're headed.

Join the discussion here: https://www.reddit.com/r/anycubic/comments/12a2fqp/any_interest_in_a_kobra_max_klipper_package/

This printer.cfg has print area mesh enabled by default. You just need to follow the steps outlined in the notes for the macro if you are using Cura, or follow the link contained to set up a different slicer.

From messing with it and the strain gauge, I found that the device Anycubic chose is inaccurate if not A) hot and B) heated at least to print temperature. There are two problems:
**
1. the extruder tension changes when the filament inside is cold/tugging on it while moving around

2. any little bit of solid plastic on the nozzle tip will ruin what you had previously set for z-offset after the mesh is complete.**

My config is optimized for this. You can home the printer cold just to get it ready if you want, but the START_PRINT macro makes up for it. It will heat, clear the mesh, re-home HOT, mesh the print area, then load the mesh and begin. I am getting very good results with this method so far, and have put quite a bit of time into making it work right. I've been able to set a hard z-offset and not play with it thus far.

Changed microsteps for X/Y to 64 as per invisiblek:

https://github.com/invisiblek/klipper_config/tree/kobraplus

This seems to have fixed Y axis layer shifting.

Added load/unload filament macros. Do not use these while printing, it will turn off your heaters and LEDs and change the temperature.

Added my model for an Orange Pi Zero 2 enclosure which will fit the frame rail behind the screen. This enclosure accomodates having a fan attached to the inside for a clean look.
