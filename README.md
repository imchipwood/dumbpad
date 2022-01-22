# dumbpad

dumbpad is a simple macropad with support for up to two rotary encoders, designed to use [QMK](https://qmk.fm/) firmware.

## Gallery

![v0.2 and v0.7 revisions in various layouts](https://i.imgur.com/c3YBNp0.jpg)

Top two boards are v0.2, bottom two are v0.7. Bottom right is v0.7 with components soldered to the bottom, moving the rotary encoder to the right side.

![v0.6_dualencoder by chicocode](https://i.imgur.com/OkSRXWT.jpg)

[v0.6_dualencoder](https://www.github.com/imchipwood/dumbpad/tree/v0.6_dualencoder) by chicocode, boards likely manufactured by [JLC PCB](https://www.jlcpcb.com)

## In this repository

This repo is separated into three main folders:

- [combo](./combo) houses the main PCB design which includes support for up to two rotary encoders and three status LEDs intended for the Pro Micro.
- [combo_oled](./combo_oled) was created by [KEEBD](https://keebd.com) and replaces the layer LED/Resistors with OLED display support and converted to KiCad.
- [combo_teensy](./combo_teensy) is the same as [combo](./combo) but designed for the Teensy2.0.
- [reversible](./reversible) is an older, single-encoder revision using custom reversible Cherry MX sockets to allow the rotary encoder to be moved to the right side.

Each folder includes the Eagle files as well as exported Gerber files for manufacturing. These folders also include readmes specific to those designs - check them for more info.

### Features

#### Status Indicator LEDs

All PCB revisions in this branch support up to three LEDs.

| LED position on PCB | LED name in QMK software | LED default behavior |
|:-:|:-:|:-:|
| right | LED_00 | 1s bit in binary layer indication |
| center | LED_01 | 2s bit in binary layer indication |
| left | LED_02 | numlock indicator |

LED_00 (right) and LED_01 (center) indicate the layer by displaying the layer number in binary:

| center LED | right LED  |   layer    |
|:----------:|:----------:|:----------:|
| off        | off        | 0 (main)   |
| off        |  on        | 1          |
|  on        | off        | 2          |
|  on        |  on        | 3          |

LED behavior can be changed in the QMK software if you'd like them to do something else. See [v1x.c](https://github.com/imchipwood/qmk_firmware/blob/dumbpad_refactor/keyboards/dumbpad/v1x/v1x.c) for reference.

#### (Optional) Reset Button

[combo](./combo) and [reversible](./reversible) have a 6mm switch socket that is optional to include when building your dumbpad. This socket shorts RST to GND to make it easy to enter the bootloader. This is not included in the [combo_teensy](./combo_teensy) design as the Teensy has a reset button already.

If you don't want to solder this switch, make sure to include the [RESET](https://docs.qmk.fm/#/quantum_keycodes) keycode somewhere in your keymap. If you don't include this keycode, you can still enter the bootloader by shorting RST to GND while plugging in the USB cable.

## PCB Dimensions

97mm x 78.5mm rectangle, with chamfered corners (chamfered edge is 2.828mm long)

### Mounting holes

There are four 2mm holes in a 40mm square centered at (x, y) 58.575mm, 39.425mm. These holes are not plated.

Mounting hole coordinates:

| x (mm) | y (mm) |
|:------:|:------:|
| 38.575 | 19.425 |
| 38.575 | 59.425 |
| 78.575 | 19.425 |
| 78.575 | 59.425 |

## Notes

- No case is available but one is in the works. If not using a case, it is recommended that you place some adhesive rubber feet on the bottom to reduce strain on the PCB.
  - In particular, clickable rotary encoders take significantly more force to click than a keyboard switch, so place a rubber foot directly under or at least near any encoders

## Making the PCB

Submit one of the gerber zips to your preferred manufacturer (or the Eagle .brd file if supported).
