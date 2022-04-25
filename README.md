# md001 juniper
Juniper Eurorack Module.

## firmware update instructions
Firmware may be updated by downloading one of the release binaries found in this repository. Firmware is upgraded by copying a release binary to the `FAT32` formatted microsd card of the device and naming the file `fw.bin`. On powerup hold the `PHASE/CH7` button, the bootloader of the device will then flash the device with the desired firmware and then restart.

## sdcard requirements
The microsd card must be formatted with `FAT32` and use `Master Boot Record (MBR)`. Not much space is required but 4GB sdcards seem to be the cheapest available.

## calibration instructions
In some rare cases the firmware may be required to wipe the user calibration data. In this scenario upon rebooting the device will boot into the calibration screen. To calibrate the device, a multimeter with reasonable accuracy will be required (such as a Fluke 101).
To manually begin the calibration process on powerup hold the `OFFSET/CH8` button.

## release information
Currently the firmware is in closed early beta with various known bugs and some features not fully implemented.

## bug reporting
For any issues you find with the device or firmware, please create a new issue within this repository. Please ensure to list the device `revision` and `firmware`.
