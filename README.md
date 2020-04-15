# dumbpad
Designed by [imchipwood](https://www.github.com/imchipwood) in Portland, Oregon, USA

Special thanks to [QMK](https://www.qmk.fm) for open-source keyboard firmware

## Description
dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro but any ATmega32u4-based microcontroller using the same form factor should work

It is designed to run [QMK firmware](https://github.com/qmk/qmk_firmware) - check [qmk_firmware/keyboards/dumbpad](https://github.com/qmk/qmk_firmware/tree/master/keyboards/dumbpad) for compiling & uploading instructions

#### dumbpad v0.2, PCB by [OSH Park](https://www.oshpark.com)
![dumbpad](https://i.imgur.com/sS3fq1Z.jpg)
### Eagle PCB render
![dumbpad](dumbpad.png)

### Parts
* 16x Cherry-style mechanical switches
* 17x 1n4148 diodes (thru hole)
* 1x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
* 1x EC11 rotary encoder with pushbutton (7-pin)
* (optional) 1x 6mm tactile switch (to reset MCU)

#### Notes
- No case is currently available
- To avoid damaging the PCB and prevent it from sliding around, put five rubber feet on the bottom of the PCB
  - place one directly under the rotary encoder as it takes significant force to press
  - place the others in the corners and one in the center

## Making the PCB
Submit the `.brd` file to your preferred PCB manufacturer - be mindful of minimum quantity requirements.

### OSH Park - USA PCB Manufacturing
Shameless Portland, Oregon company plug - [OSH Park](https://www.oshpark.com) is a fast and reliable manufacturer, combining multiple individual orders into a single panel to minimize end-user costs. dumbpad is just under $60 for 3 copies through OSH Park.