# dumbpad/combo

This folder houses the dumbpad "combo" design - this layout uses custom "combo" Cherry MX + EC11 rotary encoder sockets that allow a single PCB design to support both single- and dual-encoder layouts.

## Compiling QMK

The [QMK Configurator](https://config.qmk.fm/#/dumbpad/v1x/LAYOUT) can compile the various dumbpad versions
with basic rotary encoder support. The default rotary encoder actions are as follows:

| Layer | Clockwise | Counter-clockwise |
|:-:|:-:|:-:|
| 1 | KC_MS_R (move mouse right) | KC_MS_L (move mouse left) |
| 2 | KC_EQUALS (Adobe "increase") | KC_MINUS (Adobe "decrease") |

If you want the encoder to do something else, you will need to clone the [qmk_firmare](https://github.com/qmk/qmk_firmware) repository and modify the rotary encoder code. The [QMK docs](https://docs.qmk.fm/#/newbs) can help you with this.

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

![single encoder](https://i.imgur.com/8ZPz1gFl.jpg)

### Dual-Encoder Bottom

One dual-encoder configuration has encoders in the bottom two corners of the 4x4 grid, and switches in the rest of the grid. The socket in column 0 is left empty.

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |__X__|  s  |  s  |__X__|

![dual-encoder bottom](https://i.imgur.com/QCqKDMSl.jpg)

### Dual-Encoder Top

Another dual-encoder configuration has encoders in the top two corners of the 4x4 grid, and switches in the rest of the grid. The socket in column 0 is left empty.

| C0  | C1  | C2  | C3  | C4  |
|:---:|:---:|:---:|:---:|:---:|
|     |__X__|  s  |  s  |__X__|
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |
|     |  s  |  s  |  s  |  s  |

![dual-encoder top](https://i.imgur.com/Rq6ox2Ol.jpg)

### No-Encoder

You may also choose not to use any rotary encoders if you like!

### Bill Of Materials

- Cherry-style mechanical switches
- EC11 rotary encoder with pushbutton (7-pin) - one or two depending on your desired configuration
- 1n4148 diodes (thru hole) - one per switch and rotary encoder (if using clickable encoder(s))
- 1x Arduino Pro Micro or pin-compatible ATmega32u4-based MCU
- (optional) 3x 3mm LEDs
  - (optional) 3x 3mm resistors (for limiting current in LEDs)
- (optional) 6mm SPST switch for resetting MCU
