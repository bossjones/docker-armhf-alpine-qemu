# docker-armhf-alpine-qemu
Building an armhf alpine image with qemu binary


# Alpine + QEMU + ARM (armhf)

[![Build Status](https://img.shields.io/docker/build/bossjones/armhf-alpine-qemu.svg)](https://hub.docker.com/r/bossjones/armhf-alpine-qemu)
[![Layers](https://images.microbadger.com/badges/image/bossjones/armhf-alpine-qemu.svg)](https://microbadger.com/images/bossjones/armhf-alpine-qemu "Get your own image badge on microbadger.com")

This project enables building a *Docker* image to allow running *32-bits ARM*
*Alpine Linux* builds on non-arm hosts (like [Travis](https://travis-ci.org) build agents).

## Usage

Before building images from this image or running containers from those on `x86`
architecture execute the following command:

`docker run --rm --privileged multiarch/qemu-user-static:register --reset`

As described in its [GitHub project](https://github.com/multiarch/qemu-user-static)
this will register the *static QEMU binary* that exists in this base image
for all supported processors.


## Inspiration
- https://github.com/rycus86/docker-arm64v8-debian-qemu


## Differences between arm64 and aarch64

### https://stackoverflow.com/questions/31851611/differences-between-arm64-and-aarch64

It seems that ARM64 was created by Apple and AARCH64 by the others, most notably GNU/GCC guys.

After some googling I found this link:

The LLVM 64-bit ARM64/AArch64 Back-Ends Have Merged

So it makes sense, iPad calls itself ARM64, as Apple is using LLVM, and Edge uses AARCH64, as Android is using GNU GCC toolchain.
