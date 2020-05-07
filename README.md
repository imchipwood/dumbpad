# dumbpad
Designed by [imchipwood](https://www.github.com/imchipwood) in Portland, Oregon, USA

Special thanks to [QMK](https://www.qmk.fm) for open-source keyboard firmware

## Description
dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro but any ATmega32u4-based microcontroller using the same form factor should work

It is designed to run [QMK firmware](https://github.com/qmk/qmk_firmware) - check [qmk_firmware/keyboards/dumbpad](https://github.com/qmk/qmk_firmware/tree/master/keyboards/dumbpad) for compiling & uploading instructions

## v1.0 features:

- a third LED is used to indicate if numlock is enabled
- A debug version of each layout is available - it adds extra Pro Micro header holes to facilitate testing extra hardware

#### v0.6_dualencoder by chicocode:
![dumbpad](https://i.imgur.com/OkSRXWT.jpg)
#### Eagle PCB render
![dumbpad](dumbpad.png)

### Parts
* 14x Cherry-style mechanical switches
* 16x 1n4148 diodes (thru hole)
* 1x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
* 2x EC11 rotary encoder with pushbutton (7-pin)
* (optional) 1x 6mm tactile switch (reset button)
* (optional) 3x 3mm LEDs
* (optional) 3x 330ohm 1/8w or similar resistors for the LEDS (not needed if not adding LEDs)

#### Notes
- No case is currently available - however, there are mounting holes in all v1.0 versions in a 38.1mm square at these positions (from bottom left of PCB):
  - 39.525, 58.475
  - 39.525, 20.375
  - 77.625, 58.475
  - 77.625, 20.375
- To avoid damaging the PCB and prevent it from sliding around, put rubber feet on the bottom of the PCB
  - place feet directly under the rotary encoder(s) as they take significant force to press
  - place the others in the corners and one in the center

## Making the PCB
Submit the `.brd` file to your preferred PCB manufacturer - be mindful of minimum quantity requirements.

### OSH Park - USA PCB Manufacturing
Shameless Portland, Oregon company plug - [OSH Park](https://www.oshpark.com) is a fast and reliable manufacturer, combining multiple individual orders into a single panel to minimize end-user costs. dumbpad is just under $60 for 3 copies through OSH Park.
