# armwrestler-fixed

The original source for armwrestler can be found [here](https://github.com/mic-/armwrestler).

# Fixes
 - Initializes TCM properly and mirrors from 0x0..0x1FFFFFF. Original armwrestler places its stack in a region it expects TCM to be mapped to, however the crt0 never initializes TCM (oops!)
 - Fixes erroneous write to DMA2CNT_L when trying to clear IME.
 - Maps ARM9 binary to secure area region of cartridge and includes E7FFDEFF magic (not important for running on hardware, but allows firmware boot in emulators).
