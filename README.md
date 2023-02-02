
 <a href="http://www.amitmerchant.com/electron-markdownify"><img src="https://imgur.com/9RIxP0s.png" alt="dumbpad logo" width="150"></a>


dumbpad is a simple macropad with support for up to two rotary encoders, designed to use [QMK](https://qmk.fm/) firmware.

## Gallery

![v0.2 and v0.7 revisions in various layouts](https://i.imgur.com/c3YBNp0.jpg)

Top two boards are v0.2, bottom two are v0.7. Bottom right is v0.7 with components soldered to the bottom, moving the rotary encoder to the right side.

## In this repository

This repo is separated into five main folders:

- [combo](./combo) houses the main PCB design which includes support for up to two rotary encoders and three status LEDs intended for the Pro Micro.
- [combo_oled](./combo_oled) was created by [KEEBD](https://keebd.com) and replaces the layer LED/Resistors with OLED display support and converted to KiCad.
- [combo_teensy](./combo_teensy) is the same as [combo](./combo) but designed for the Teensy2.0.
- [reversible](./reversible) is an older, single-encoder revision using custom reversible Cherry MX sockets to allow the rotary encoder to be moved to the right side.
- [hotswap_rgb - v3.x](./hotswap_rgb) dumbpad featuring per-key RGB and Hotswap sockets

Each folder includes the Eagle or KiCad files as well as exported Gerber files for manufacturing. These folders also include readmes specific to those designs - check them for more info.

## Getting Started
To build your own dumbpad you will need to follow a couple of steps to get started. Described below are the minimal steps you will need to take to to assemble one dumbpad but every board configuration might require different steps. 
#### 1. Choose version. 
You can choose from one of the five different versions shown in the step above.
#### 2. Order your parts. 
Every board needs at least the following components but check the right folder for your parts list.
* 1 x PCB
* 16 x MX-style mechanical switches
* 17 x 1n4148 diodes (thru hole)
* 1 x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU (Or teensy for the teensy version)
* (optional) 1 x EC11 rotary encoder with pushbutton (7-pin)
* (optional) 1 x 6mm tactile switch (to reset MCU)
* LEDS and OLED required for different configurations

#### 3. Assemble your dumbpad
For this step you will need a minimum of a soldering iron and a pair of tweezers
- Solder the diodes, switches, and Arduino Pro Micro (Or teensy) to the PCB

#### 4. Flash your firmware
You can use QMK to create and flash firmware to your dumbpad. You can configure every key to you can use the QMK configurator. Head over to the [QMK configurator](https://config.qmk.fm/#/friedrich/LAYOUT) and select dumbpad/[your version]. Once you have configured your board, click on compile and then on firmware to download the firmware. Check [qmk_firmware/keyboards/dumbpad](https://github.com/qmk/qmk_firmware/tree/master/keyboards/dumbpad) for compiling & uploading instructions

Once you have downloaded a .HEX firmware file we can head over to the [QMK toolbox](https://github.com/qmk/qmk_toolbox/releases) and flash the firmware. Plug in your dumbpad to your computer and set your QMK toolbox to ATmega32U4 for most Arduino Pro Micros. You will need to press your 6mm tacticle switch twice to enter the bootloader, wait for your computer to reconize the dumbpad and click on flash.




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

[combo](./combo), [hotswap_rgb](./hotswap_rgb) and [reversible](./reversible) have a 6mm switch socket that is optional to include when building your dumbpad. This socket shorts RST to GND to make it easy to enter the bootloader. This is not included in the [combo_teensy](./combo_teensy) design as the Teensy has a reset button already.

If you don't want to solder this switch, make sure to include the [RESET](https://docs.qmk.fm/#/quantum_keycodes) keycode somewhere in your keymap. If you don't include this keycode, you can still enter the bootloader by shorting RST to GND while plugging in the USB cable.

## PCB Dimensions and Cases

97mm x 78.5mm rectangle, with chamfered corners (chamfered edge is 2.828mm long).

There are several cases available for printing, some can be found in `./case`. Another nice case was designed by [f00k3r](https://twitter.com/f00k3r) and uploadead to printables: [Dumbpad Hotswap Case](https://www.printables.com/model/200528-dumbpad-hotswap-case).

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

- In particular, clickable rotary encoders take significantly more force to click than a keyboard switch, so place a rubber foot directly under or at least near any encoders

## Making the PCB

Every parts list includes at least one PCB. You can order a PCb yourself by different manufactures like; [PCB way](https://www.pcbway.com/) or [JLC Pcb](https://jlcpcb.com/) Submit one of the gerber zips from the folder of the type of board you want to make to your preferred manufacturer (or the Eagle .brd file if supported).

![render of boards](https://i.imgur.com/op5A2IL.png)
