# ADV360-PRO-ZMK

## Edit keymap
Edit config/adv360.keymap\
ZMK Tokens: https://zmk.dev/docs/codes

### Layer colors
The layer LED will change color depending on which layer you're on:
- 0 off
- 1 white
- 2 blue
- 3 green\
  I thought it was good to get the layer with he bootloader key off the green layer
- 4 red  
  Moved the Mod layer to here with a dummy layer in place of layer 3
- 5 purple
- 6 cyan
- 7 yellow
- 8+ off?  
  Once I got to layer 8 & 9, it appeared the LED no longer lit up for layer changes.

### GUI Editing
Not recommended due to the formatting it outputs (2022/12/03)\
Kinesis mentions: https://kinesiscorporation.github.io/Adv360-Pro-GUI  
But it appears to be broken. It will only display the default configuration.\
For editing via GUI, you can use: https://nickcoutsos.github.io/keymap-editor  
However, the autoformatting will slaughter your keymap file for later manual editing.  
nickcoutsos is still good for viewing/reference though.

## To build Firmware in GitHub Actions

### Setup

1. Fork this repo.
2. Enable GitHub Actions on your fork.

### Build firmware

1. Push a commit to trigger the build.
2. Download the artifact.

## Local building in a container

### Setup

#### Software

Either Podman or Docker is required, Podman is preferred if both are present.\
Make is also required

#### Windows specific
If compiling on Windows use WSL2 and Docker [Docker Setup Guide](https://docs.docker.com/desktop/windows/wsl/).\
Install make using `sudo apt-get install make`.\
The repository can be cloned directly into the WSL2 instance or accessed through the C: mount point WSL provides by default (`/mnt/c/path-to-repo`).

### Build firmware

1. Execute `make`.
2. Check the `firmware` directory for the latest firmware build.

### Cleanup

The built docker container and compiled firmware files can be deleted with `make clean`.

## Flashing firmware

Follow the programming instruction on page 8 of the [Quick Start Guide](https://kinesis-ergo.com/wp-content/uploads/Advantage360-Professional-QSG-v8-25-22.pdf) to flash the firmware.

## Other support

Further support resources can be found on Kinesis.com
https://kinesis-ergo.com/support/kb360pro/#firmware-updates
https://kinesis-ergo.com/support/kb360pro/#manuals
