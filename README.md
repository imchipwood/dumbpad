# dumbpad
Designed by [imchipwood](https://www.github.com/imchipwood) in Portland, Oregon, USA

Special thanks to [QMK](https://www.qmk.fm) for open-source keyboard firmware

## Description

dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro but any ATmega32u4-based microcontroller using the same form factor should work

It is designed to run [QMK firmware](https://github.com/qmk/qmk_firmware) - check [qmk_firmware/keyboards/dumbpad](https://github.com/qmk/qmk_firmware/tree/master/keyboards/dumbpad) for compiling & uploading instructions

## v1.x features

- a third LED is used to indicate if numlock is enabled
- v1.1 uses combined Cherry MX switch & EC11 rotary encoder sockets. At most, two encoders can be connected
  - Assuming a 5x4 grid (column = x, row = y) where the bottom left is 0, 0, these encoder signals are connected together:
    - (0, 0), (1, 0), (1, 3)
    - (4, 0), (4, 3)
    - two encoders can be used as long as they're not connected as described above

### v0.6_dualencoder by chicocode

![dumbpad](https://i.imgur.com/OkSRXWT.jpg)

### Eagle PCB render

![dumbpad](dumbpad.png)

### Parts

- 14x Cherry-style mechanical switches
- 16x 1n4148 diodes (thru hole)
- 1x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
- 2x EC11 rotary encoder with pushbutton (7-pin)
- (optional) 1x 6mm tactile switch (reset button)
- (optional) 3x 3mm LEDs
- (optional) 3x 330ohm 1/8w or similar resistors for the LEDS (not needed if not adding LEDs)

#### Notes

- No case is currently available, but v1.0 has 2mm mounting holes in a 40mm square centered at x=58.575mm, y=39.425mm (from the bottom left)
  - 38.575, 19.425
  - 38.575, 59.425
  - 78.575, 19.425
  - 78.575, 59.425
- To avoid damaging the PCB and prevent it from sliding around, put rubber feet on the bottom of the PCB
  - place feet directly under the rotary encoder(s) as they take significant force to press
  - place the others in the corners and one in the center

## Making the PCB

Submit the `.brd` file to your preferred PCB manufacturer - be mindful of minimum quantity requirements.
