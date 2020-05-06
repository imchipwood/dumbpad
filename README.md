# dumbpad
Designed by [imchipwood](https://www.github.com/imchipwood) in Portland, Oregon, USA

Special thanks to [QMK](https://www.qmk.fm) for open-source keyboard firmware

## Description
dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro but any ATmega32u4-based microcontroller using the same form factor should work

It is designed to run [QMK firmware](https://github.com/qmk/qmk_firmware) - check [qmk_firmware/keyboards/dumbpad](https://github.com/qmk/qmk_firmware/tree/master/keyboards/dumbpad) for compiling & uploading instructions

### Revisions
- v0.5 introduces 2x LEDs for indicating which layer is enabled, accurately representing up to 4 layers
- v0.6_dualencoder is a true 4x4 macropad with two rotary encoders - one in each bottom corner
- v0.6_dualencoder_top is the same as v0.6_dualencoder but the encoders are moved to the top corners
- v0.7 PCB is flippable. Two jumpers must be soldered:
  - Encoder on left (default layout) - solder the left side of the jumpers to the center
  - Encoder on right (PCB upside down) - solder the right side of the jumpers to the center
- v1.0 PCB adds a 3rd LED - default use is to indicate if NUMLOCK is on

#### dumbpad v0.2, PCB by [OSH Park](https://www.oshpark.com)
![dumbpad](https://i.imgur.com/sS3fq1Z.jpg)
#### Dual-encoder version by chicocode:
![dumbpad](https://i.imgur.com/OkSRXWT.jpg)
#### Eagle PCB render
![dumbpad](dumbpad.png)

### Parts
* 16x Cherry-style mechanical switches
* 17x 1n4148 diodes (thru hole)
* 1x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
* 1x EC11 rotary encoder with pushbutton (7-pin)
* (optional) 1x 6mm tactile switch (to reset MCU)
* (optional) 3x 3mm LEDs (whatever color)
* (optional) 3x 330ohm or similar resistors for the LEDS (not needed if not adding LEDs)

#### Notes
- No case is currently available, but v1.0 has mounting holes in a 38.1mm square at these positions (from bottom left of PCB):
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