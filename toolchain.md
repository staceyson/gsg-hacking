# GSG toolchain

Want to build software for your Atari GSG?
Use our GCC-based toolchain.

## Building the toolchain

On a Linux computer, run the `build-sysroot.sh` script:

    $ ./build-sysroot.sh toolchain

This script will create a `build/src` directory with source code and temporary build artifacts, and a `build/usr/bin` directory with the compiler, linker, etc.

`build-sysroot.sh` requires a bunch of tools and libraries to be installed on your computer.
The list of build-time dependencies can be found in `Dockerfile`.

To avoid installing tools and libraries on your computer manually, you can build the toolchain in a Docker container:

    $ sudo docker build --tag gsg-hacking . && sudo docker run -it --mount "type=bind,source=$PWD,destination=$PWD" gsg-hacking:latest "${PWD}/build-sysroot.sh" toolchain
