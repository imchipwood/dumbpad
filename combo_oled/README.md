# dumbpad - OLED (aka v1.2)

Designed by [KEEBD](https://www.keebd.com).

## Description

Version of the original dumbpad but with support for an OLED display in place of the LED's and resistors.

### Revisions

- 1.2 Initial published PCB


#### dumbpad v1.2

![pcbs](img/dumbpad_oled_v1_2_pcbs.png)
![finished](img/dumbpad_oled_v1_2_finished.png)


#### Renders

![front](img/dumbpad_oled_v1_2_front.png)
![back](img/dumbpad_oled_v1_2_back.png)


### Parts

* 16 x Cherry-style mechanical switches
* 17 x 1n4148 diodes (thru hole)
* 1 x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
* 1 x 0.91" 128X32 OLED Display
* (optional) 1 x EC11 rotary encoder with pushbutton (7-pin)
* (optional) 1 x 6mm tactile switch (to reset MCU)

## OLED Firmware

The OLED firmware is different and can be found here [Firmware](https://github.com/keebd/qmk_firmware/tree/keebd/keyboards/dumbpad/combo_oled)

## Making the PCB

Submit either the KiCad `.kicad_pcb` or the gerber files to your prefered PCB manufacturer.
