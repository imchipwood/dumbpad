# dumbpad

dumbpad is a simple macropad with support for up to two rotary encoders, designed to use [QMK](https://www.qmk.fm) firmware.

## Gallery

![v0.2 and v0.7 revisions in various layouts](https://i.imgur.com/c3YBNp0.jpg)

Top two boards are v0.2, bottom two are v0.7. Bottom right is v0.7 with components soldered to the bottom, moving the rotary encoder to the right side.

![v0.6_dualencoder by chicocode](https://i.imgur.com/OkSRXWT.jpg)

[v0.6_dualencoder](https://www.github.com/imchipwood/dumbpad/tree/v0.6_dualencoder) by chicocode, boards likely manufactured by [JLC PCB](https://www.jlcpcb.com)

## In this repository

This repo is separated into three main folders:

- [combo](./combo) houses the main PCB design which includes support for up to two rotary encoders and three status LEDs intended for the Pro Micro.
- [combo_teensy](./combo_teensy) is the same as [combo](./combo) but designed for the Teensy2.0.
- [reversible](./reversible) is an older, single-encoder revision using custom reversible Cherry MX sockets to allow the rotary encoder to be moved to the right side.

Each folder includes the Eagle files as well as exported Gerber files for manufacturing. These folders also include readmes specific to those designs - check them for more info.

### Features

#### Status Indicator LEDs

All PCB revisions in this branch support up to three LEDs.

- left-most LED: numlock indicator
- center and right-most LED: layer indication, up to four layers (main layer + 3 others) by displaying in binary:

| center LED | right LED  |   layer    |
|:----------:|:----------:|:----------:|
| off        | off        | 0 (main)   |
| off        |  on        | 1          |
|  on        | off        | 2          |
|  on        |  on        | 3          |

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
