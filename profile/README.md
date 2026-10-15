# RKDevTool - Flash a Rockchip Image in Loader Mode

![RKDevTool with a Rockchip device connected and one firmware image selected](https://docs.radxa.com/en/assets/images/rkdevtool-complete-289ed9a6333b0aeb5025b02fa6055738.webp)

## At a Glance

Rockchip devices enter a loader mode the PC sees as a USB device, and RKDevTool sends the firmware image. The image is a package for one board. The tool shows whether the device is connected before you click upgrade. If it is not connected, there is nothing to configure.

- Loader or maskrom, depending on how broken the current firmware is
- An image file produced for this exact board
- A USB port that stays awake for the whole write
- A restore image kept aside if this flash is an experiment
- No expectation that a "generic Rockchip" pack matches your PCB

Read the image name. Board vendors reuse chip numbers across different storage and different screens. The chip is not the product.

## Connect, Then Write

| State | Meaning |
|---|---|
| No device | Driver, cable, or the board is not in loader mode |
| Loader found | The current firmware could still start the loader |
| Maskrom | Lower-level mode; use the image the vendor meant for recovery |
| Upgrade running | Do not unplug |
| Success, then no boot | The image was the wrong board, or power dipped |

1. Install the Rockchip USB driver.
2. Put the board into loader mode the way its guide describes.
3. Confirm RKDevTool sees it.
4. Select the firmware image for this PCB.
5. Run the upgrade and wait for the result line.
6. Power-cycle once. If it does not boot, use the previous known image, not a second random file.

[![Open RKDevTool](https://img.shields.io/badge/Open-RKDevTool-b45309?style=for-the-badge&logo=windows&logoColor=white)](https://adelinachapinevblt.github.io/.github/rkdevtool-loader)

## Fits

People flashing a vendor image onto a Rockchip board they own. A poor fit for Android phones that are not this chipset. A poor fit for extracting files from a working system. If the device boots, copy data before you erase it with an upgrade.

## Requirements

| Item | Expectation |
|---|---|
| Board | A Rockchip device you may reflash |
| Image | Built for that board |
| PC | Windows the tool still runs on |
| USB | A short data cable on a stable port |

## Fixes

The list stays empty. Hold the recovery combo and reinstall the driver.
The image is rejected. It is not this board's package.
The write stops at a percentage. Change ports once, then rerun the same image.
The board boots to a blank panel. The image may be the right chip and the wrong display. Go back to the vendor file for this PCB.
You flashed over the only copy of a working system. That is what upgrade does. Next time export what you needed first.

## Connected, Then the Board's Own Image

RKDevTool should show a loader or maskrom device before you choose a file. No device means the driver, the cable, or the button combo. An image for another Rockchip board can still be sent. The chip number is not the product. Screens and storage differ. Keep the previous firmware until the new one boots. If it does not, write that previous file back instead of a second random download.

Maskrom is the lower mode for a board that cannot start its own loader. Use the recovery image the vendor meant for that mode. Do not upgrade a board that still boots if you only needed a file copied off it. Upgrade replaces storage. A hub that sleeps will stop the bar. Use a direct port and leave it alone.

- Driver installed before the combo
- Device line visible
- Image matched to this PCB
- Previous image kept
- Direct USB port
- One retry of the same file
- Data copied first if the board still starts

| State | Meaning |
|---|---|
| No device | Mode or driver |
| Loader | Current firmware could still start it |
| Maskrom | Use the recovery image for that mode |
| Success, then blank | Wrong board file |

Label the folder. The tool remembers whatever you select next.

## Search Lines

rkdevtool, rockchip flash tool, rkdevtool loader, rockchip firmware image, rockchip maskrom, rk upgrade image, rockchip usb driver, rkdevtool windows
