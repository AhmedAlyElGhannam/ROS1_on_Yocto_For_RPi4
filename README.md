# ROS1_on_Yocto_For_RPi4

## Introduction

### Author's Note
This README file is a step-by-step tutorial on how to add and use ROS on a Yocto image for Raspberry Pi 4. In the process of research, I have found that the "official" `meta-ros` layer is depricated, full of bugs, and most importantly has no support for the latest LTS version of The Yocto Project: Kirkston. So, here I will document the entire process of building it: starting from cloning `poky` and `openembedded` to running `roscore` one the Pi.

## Target Hardware Specifications
As stated earlier, the target hardware is a Raspberry Pi 4 8GB Rev 1.5C with the following pin configuration. Knowing the pin configuration will be important later on in order to communicate with the Pi later on via a serial terminal like `gtkterm` using a USB-to-TTL device as shown below.
_pi photo_
_ttl photo_

## Build Device Specifications
I have built this Yocto image on a PC with the specifications stated below. I made sure to record the time it took me to build the image for reference. Bare in mind that performance may differ duo to multiple reasons such as: temperature---a laptop is more likely to throttle than a PC; disk speed---I built it entirely on an SSD and it took over 2 hours, I can hardly imagine how long it would take to build an image on an HDD; and lastly the performance of your machine---I am running a native/real Ubuntu 22.04 machine, not a VM.
_pc drip_

With all the exposition out of the way, let us begin.

## Setting Up Yocto Project Essentials
