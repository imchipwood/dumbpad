# dumbpad
dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro but any microcontroller using the same form factor should work

It is designed to run QMK firmware. https://github.com/qmk/qmk_firmware

## Parts
* 16x Cherry-style mechanical switches
* 18x 10KOhm resistors (current form factor uses 0603, may change in future versions)
* 1x Pro Micro ATmega32u4
* 1x EC11 rotary encoder

## Making the PCB
https://www.oshpark.com is the recommended service for creating PCBs. 3x PCBs is just under $60 from them.
https://www.oshstencils.com is the recommended service for creating SMD stencils.

At both sites, simply upload the .brd file to create the project and order. With only 18x SMD resistors spaced quite far apart, the stencil isn't even needed - soldering by hand is simple.
