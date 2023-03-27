# ADV360-PRO-ZMK

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

## Edit keymap

This can be done manually or with the GUI.
Be aware of which files are read and compiled if going back and forth between these.

### Edit keymap manually

Edit config/adv360.keymap
ZMK Tokens: https://zmk.dev/docs/codes

### Edit keymap with GUI

https://kinesiscorporation.github.io/Adv360-Pro-GUI  
This reads in config/keymap.json and outputs config/adv360.keymap & config/keymap.json

### Layer colors

The layer LED will change color depending on which layer you're on:
- 0 off
- 1 white
- 2 blue
- 3 green\
  I thought it was good to get the layer with the bootloader key off the green layer
- 4 red  
  Moved the Mod layer to the red layer as a warning by placing a dummy/blank layer to skip white layer 1 and remapped mo & tog keys appropriately
- 5 purple
- 6 cyan
- 7 yellow
- 8+ off?  
  Once I got to layer 8 & 9, it appeared the LED no longer lit up for layer changes.
There might be a better way to assign colors, but I haven't found it and not worth digging as easy as this is.

## Other support

Further support resources can be found on Kinesis.com
https://kinesis-ergo.com/support/kb360pro/#firmware-updates
https://kinesis-ergo.com/support/kb360pro/#manuals
