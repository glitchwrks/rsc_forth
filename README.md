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
