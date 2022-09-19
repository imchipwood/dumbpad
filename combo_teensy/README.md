# dumbpad/combo

This folder houses the dumbpad "combo_teensy" design - this layout uses custom "combo" Cherry MX + EC11 rotary encoder sockets that allow a single PCB design to support both single- and dual-encoder layouts. It uses Teensy2.0 microcontroller instead of a Pro Micro

## Eagle PCB render

![dumbpad](dumbpad.png)

## Single- vs Dual-Encoder Support

The combined Cherry MX/encoder sockets allow single- and dual-encoder configurations.

The only rule when using two encoders is that there cannot be two encoders on the left side at once, or two on the right side.
This table shows where the encoders are in the switch grid ("X" for encoder, "s" for switch):

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |__X__|  s  |  s  |__X__|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|__X__|__X__|  s  |  s  |__X__|

- The three encoders in columns C0 and C1 are connected to each other
- The two encoders in column C4 are connected to each other

So, if doing dual encoders, one must be in column C4 and the other in either C0 or C1. Three or more encoders will not work.

The following sections describe the configurations that the default keymaps in QMK are designed for.

### Single-Encoder (Default Configuration)

In the default configuration, the encoder is in column 0, the bottom left corner below the Pro Micro. All other sockets are filled with switches.

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|__X__|  s  |  s  |  s  |  s  |

### Dual-Encoder Bottom

One dual-encoder configuration has encoders in the bottom two corners of the 4x4 grid, and switches in the rest of the grid. The socket in column 0 is left empty.

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |__X__|  s  |  s  |__X__|

### Dual-Encoder Top

Another dual-encoder configuration has encoders in the top two corners of the 4x4 grid, and switches in the rest of the grid. The socket in column 0 is left empty.

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |__X__|  s  |  s  |__X__|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |

### No-Encoder

You may also choose not to use any rotary encoders if you like!

### Bill Of Materials

1 x PCB
16 x MX-style mechanical switches
17 x 1n4148 diodes (thru hole)
1 x Teensy2.0 
1 x or 2 x EC11 rotary encoder with pushbutton (7-pin)
- (optional) 3x 3mm LEDs
- (optional) 3x 3mm resistors (for limiting current in LEDs)
- (optional) 6mm SPST switch for resetting MCU


