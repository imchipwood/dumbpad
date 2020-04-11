# dumbpad

Single-encoder version:
![dumbpad](https://i.imgur.com/sS3fq1Z.jpg)
Dual-encoder version:
![dumbpad](https://i.imgur.com/OkSRXWT.jpg)
Eagle PCB render:
![dumbpad](dumbpad.png)

dumbpad is a simple 4x4 macro/numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro running [QMK firmware](https://github.com/qmk/qmk_firmware).

The EC11 rotary encoder used has a push-button, which technically makes this a 17-switch macro/numpad. The default behavior of the rotary encoder is to move the mouse left/right - the intention is to be used on slider-type controls such as brightness, RGB values, etc. found in video/photo editing software.

## v0.7 Features
* PCB can be flipped upside down to allow moving the rotary encoder to the right side. This required four small jumpers which MUST be soldered regardless of which side you use the encoder on.
  * Encoder on left (default layout) - solder the left side of the jumpers to the center
  * Encoder on right (PCB upside down) - solder the right side of the jumpers to the center
* Two LEDs added for layer indication in binary (00 = default layer, 01 = layer 1, 10 = layer 2, 11 = layer 3)

## Parts
* 16x Cherry-style mechanical switches
* 17x 1n4148 diodes (thru hole)
* 1x Pro Micro ATmega32u4
* 1x EC11 rotary encoder with switch (7-pin)
* (optional) 1x 6mm tactile switch (to reset MCU - not needed most of the time as QMK has a RESET keycode)
* (optional) 2x 3mm LEDs (whatever color)
* (optional) 2x 220ohm or similar resistors for the LEDS (not needed if not adding LEDs)

## Making the PCB
https://www.oshpark.com is the recommended service for creating PCBs. 3x PCBs is roughly $60 from them. Simply upload the .brd file to create the project and order.
