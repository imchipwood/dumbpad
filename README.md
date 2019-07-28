# dumbpad
dumbpad is a simple 4x4 numpad with a rotary encoder. It is designed for the ATmega32u4-based Pro Micro.

It is designed to run QMK firmware. https://github.com/qmk/qmk_firmware

## Parts
* 16x Cherry-style mechanical switches
* 17x 1n4148 diodes (thru hole)
* 1x Pro Micro ATmega32u4
* 1x EC11 rotary encoder (7-pin)
* (optional) 1x 6mm tactile switch (to reset MCU - not needed most of the time as QMK has a RESET keycode)

## Making the PCB
https://www.oshpark.com is the recommended service for creating PCBs. 3x PCBs is roughly $60 from them. Simply upload the .brd file to create the project and order.
