<img src="https://avatars.githubusercontent.com/u/85954780?s=200&v=4" />

# md001 juniper
Juniper Eurorack Module: firmware releases, issue tracking and documentation repository.

```
firmware: 0.0.8
bootloader: 0.0.2
```

## firmware update instructions
Firmware may be updated by downloading one of the release binaries found in this repository. Firmware is upgraded by copying a release binary to the `FAT32` formatted microsd card of the device and naming the file `fw.bin`. On powerup hold the `PHASE/CH7` button, the bootloader of the device will then begin the flash procedure. Release the `PHASE/CH7` button and wait until the device finishes flashing the firmware. Once it completes it will reboot the device.

## sdcard requirements
The microsd card must be formatted with `FAT32` and use `Master Boot Record (MBR)`. Not much space is required but 4GB sdcards seem to be the cheapest available.

## calibration instructions
In some rare cases the firmware may be required to wipe the user calibration data. In this scenario upon rebooting the device will boot into the calibration screen. To calibrate the device, a multimeter with reasonable accuracy will be required (such as a Fluke 101).
To manually begin the calibration process on powerup hold the `OFFSET/CH8` button.

## bootloader flash instructions
In exceptional circumstances the bootloader may be updated, this will require manual flashing of the device.

__*Warning: Incorrect flashing can cause data loss or damage of the device!*__

The following is required:

- An `stlink v2` device
- The `stlink` utilities [found here](https://github.com/stlink-org/stlink). Ensure that the `st-flash` utility is correctly added to the PATH.
- A valid bootloader binary from this repository
- Connecting the `stlink v2` device to `md001` via the `jtag/swd` [port of the device](https://github.com/mnemonicdevices/md001/blob/main/md001-jtag-connections.png)
- Finally the device can be flashed with the updated bootloader with:

```
st-flash write <md001-bootloader-file>.bin 0x08000000
```

## release information
Currently the firmware is in closed early beta with various known bugs and some features not fully implemented.

## bug reporting
For any issues you find with the device or firmware, please create a new issue within this repository. Please ensure to list the device `revision` and `firmware`.
