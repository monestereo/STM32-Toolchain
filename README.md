### Instructions for installing STM32F4-Toolchain on Mac OSX

####Install XCode and the command line utilities

####Install Homebrew:

`ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"`

####Install dependencies:
`brew install mpfr gmp libmpc libusb-compat libftdi wget`

### Original README

arm-none-eabi toolchain builder

Binutils 2.22
GCC 4.8.0
Newlib 2.0.0
GDB 7.5.1
OpenOCD 0.6.0-rc1 (with stlink protocol enabled)
stlink master branch from https://github.com/texane/stlink

This toolchain is confirmed to work the the STM32F1- and STM32F4-Discovery boards.

Usage: Hit make and wait
Destination is overwritable by specifying TOOLCHAIN_ROOTDIR as a paramter to make
Use V=1 for verbose mode
Use CPUS=<number> to specify the number of threads. If not specified the Makefile will try to figure it out by itself
Do not use -j for the main Makefile!

example: make TOOLCHAIN_ROOTDIR=/home/user/mytoolchain

Other make targets:
	download: Fetch all sources, but don't extract or build them
	clean: Removed build-tmp directory containing temporary build files
	distclean: Like clean, but also removes downloaded source code

Dependencies (at least): libmpc, libgmp, libmpfr, libusb
