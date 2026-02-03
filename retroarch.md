# RetroArch

Before building RetroArch, you must build a cross-compiling toolchain for Atari GSG.
See [toolchain.md](toolchain.md) for instructions on building a toolchain.

## Building RetroArch

On a Linux computer, run the `build-sysroot.sh` script to download and compile RetroArch and its dependencies:

    $ ./build-sysroot.sh libraries retroarch

This will create a file called `build/usr/arm-linux-gnueabihf/usr/bin/retroarch`.

To avoid installing build-time dependencies your computer manually, you can build the RetroArch in a Docker container:

    $ sudo docker build --tag gsg-hacking . && sudo docker run -it --mount "type=bind,source=$PWD,destination=$PWD" gsg-hacking:latest "${PWD}/build-sysroot.sh" libraries retroarch

## Installing RetroArch

Copy the `build/usr/arm-linux-gnueabihf/usr/bin/retroarch` executable to your Atari GSG using either scp or a sdcard.

## Running RetroArch

Good luck!
