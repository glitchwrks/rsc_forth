# Rockwell RSC-FORTH

This repository contains ROM images, patches, and other information relating to Rockwell's RSC-FORTH, a Forth implementation for the Rockwell R6500 processor family. Specifically, the original ROMs are designed to run with the Rockwell R6501Q or R6511Q processor, which is a modified 6502 core.

Patches are provided to allow RSC-FORTH to run on the [Glitch Works R65X1Q SBC](http://www.glitchwrks.com/), loaded in via ROMFS records.

Glitch Works, LLC asserts no claim to ownership to the RSC-FORTH code, and releases all patches and other material under the GNU GPL v3.

### Original ROM Images

The `original_roms` directory contains binary images of the Rockwell RSC-FORTH ROMs, dumped from original Rockwell parts.

```
R65FK2P.BIN -- Small FORTH kernel for R6501Q
R65FR2P.BIN -- FORTH development ROM, pairs with R65FK2P

R65FK3P.BIN -- Large FORTH kernel for R6501Q
R65FR3P.BIN -- FORTH development ROM, paris with R65FK3P
```

These ROM images are described in the PDF document `rockwell_r65frx_r65fkx_rsc_forth_roms.pdf` under the `datasheets` directory. They are paired; that is, the small kernel ROM will not work with the large FORTH development ROM. Additionally, be aware that the small set configures the R6501Q differently by default.

### Datasheets

The `datasheets` directory contains PDF copies of datasheets relevant to this project. These are scans of Rockwell datasheets either scanned in directly by Glitch Works, LLC, or acquired through various Internet sources (Al Kossow's [bitsavers](http://www.bitsavers.org/), [6502.org](http://6502.org/), etc).

### Patches

The `patches` directory contains patchfiles for changing aspects of the original ROM images:

```
R65FK2P_R6501Q-SBC.patch     Patches for use with Glitch Works R6501Q SBC
R65FK3P_8_bit_serial.patch   Patches to use 8N1 for serial parameters
R65FK3P_R6501Q-SBC.patch     Patches for use with Glitch Works R6501Q SBC and 32K Memory Board
```

These are `diff`-generated patches and apply with `patch`. Once the related kernel is patched, the development ROM will work without any patches. User-created ROM images will also work without patching.

Patches for the `R65FK2P` ROM image, in addition to modifying serial configuration, put the R6501Q processor into a different mode than originally configured in the stock images. This allows operation with the Glitch Works R65X1Q SBC. With the patches applied, the major difference from the stock ROMs is that some I/O pins that are available in the original addressing mode are unavailable, as they are used for full addressing in the Glitch Works SBC. 
