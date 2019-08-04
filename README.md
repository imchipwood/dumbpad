# dumbpad

![dumbpad](https://i.imgur.com/sS3fq1Z.jpg)
![dumbpad](dumbpad.png)

dumbpad is a simple 4x4 macro/numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro running [QMK firmware](https://github.com/qmk/qmk_firmware).

The EC11 rotary encoder used has a push-button, which technically makes this a 17-switch macro/numpad. The default behavior of the rotary encoder is to move the mouse left/right - the intention is to be used on slider-type controls such as brightness, RGB values, etc. found in video/photo editing software.

v0.5 introduces 2 LEDs for indicating which layer you're on. The QMK firmware has NOT been updated to support these yet, if you are going to make a v0.5 board, please contact me and I'll update the firmware.

## Parts
* 16x Cherry-style mechanical switches
* 17x 1n4148 diodes (thru hole)
* 1x Pro Micro ATmega32u4
* 1x EC11 rotary encoder (7-pin)
* (optional) 2x 3mm LEDs (whatever color)
* (optional) 2x 220ohm or similar resistors for the LEDS (not needed if not adding LEDs)

## Making the PCB
https://www.oshpark.com is the recommended service for creating PCBs. 3x PCBs is roughly $60 from them. Simply upload the .brd file to create the project and order.
