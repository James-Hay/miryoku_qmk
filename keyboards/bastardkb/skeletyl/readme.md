# Skeletyl

A very small keyboard made for ergonomic enthusiasts.

-   Keyboard Maintainer: [Bastard Keyboards](https://github.com/Bastardkb/)
-   Hardware Supported: elite-C V4
-   Hardware Availability: [Bastardkb.com](https://bastardkb.com/)

## Building the firmware

**You must specify the shield version when compiling/flashing the firmware.**

The template is:

```shell
qmk compile -kb bastardkb/skeletyl/{VERSION}/elitec -km {KEYMAP}
```

| Shield Version  | default                                                        | via                                                        |
| --------------- | -------------------------------------------------------------- | ---------------------------------------------------------- |
| v1 (Elite-C)    | `qmk compile -kb bastardkb/skeletyl/v1/elitec -km default`     | `qmk compile -kb bastardkb/skeletyl/v1/elitec -km via`     |
| v2 (Elite-C)    | `qmk compile -kb bastardkb/skeletyl/v2/elitec -km default`     | `qmk compile -kb bastardkb/skeletyl/v2/elitec -km via`     |
| v2 (Splinky v2) | `qmk compile -kb bastardkb/skeletyl/v2/splinky/v2 -km default` | `qmk compile -kb bastardkb/skeletyl/v2/splinky/v2 -km via` |
| v2 (Splinky v3) | `qmk compile -kb bastardkb/skeletyl/v2/splinky/v3 -km default` | `qmk compile -kb bastardkb/skeletyl/v2/splinky/v3 -km via` |
| v2 (STeMCell)   | `qmk compile -kb bastardkb/skeletyl/v2/stemcell -km default`   | `qmk compile -kb bastardkb/skeletyl/v2/stemcell -km via`   |

This keyboard is made to be used with the Miryoku layout, do not use the default keymap.

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

See the [keyboard build instructions](http://docs.bastardkb.com/)

### My handwired version

#### Things to note

As this was handwired something was bound to go wrong.

I wired the diodes in the opposite direction to the original firmware, but that was and easy fix. Just change `keyboards\bastardkb\skeletyl\config.h` `DIODE_DIRECTION` to `COL2ROW`.

I think the diodes being the wrong order also meant the `MATRIX_ROW_PINS`and `MATRIX_COL_PINS` needed to change around slightly otherwise one of the thumb keys didn't work. I can't remember what was the fix as it was months ago but I'm sure it made sense.

#### Flashing

-   Install QMK MSYS
-   Use the flash command `qmk flash -kb bastardkb/skeletyl/v2/splinky_3 -km manna-harbour_miryoku -e MIRYOKU_ALPHAS=QWERTY`
-   Double tap the reset button on the RP2040 on the right hand side
-   Get a flashed keyboard...hopefully

#### Keymap

I've added the miryoku keymaps with the hope of eventually moving to the normal miryoku layout, but for now I'm just using the QWERTY alternative to easy myself in, saying that I've been using it for months now and I doubt I'll change to it.

I have tweaked the miryoku QWERTY NAV layout slightly as I was getting sick of "hjkl" being my Vim movement keys then the miryoku QWERTY movement keys being offset by one key to the right. So when I was swapping between movement keys and Vim movement keys it was pretty jarring and adding friction.

I still have work to do on the bindings/layers, I still haven't got used to the symbol keys and it's been months. I should plan them out in a way that works in my head rather then try and conform.
