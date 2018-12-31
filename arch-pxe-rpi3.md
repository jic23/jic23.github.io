# PXE Booting a Raspberry Pi 3 with Arch
# Introduction

Network booting lets the low level boot firmware in the Raspberry PI pull all of the files needed to boot down
from a wired network.

### Why would you want to do this?

PXE booting allows you to boot a Raspberry PI 3 without any SD card.  All of the files are pulled over the network.
This has several advantages:

- No SD card so cost saving if you are running lots of them.
- Very simple development cycle, particularly if you are working on the Kernel or other low level OS components as you can avoid having to constantly flash to the SD card.

# Why I wrote these notes

There are detailed instructions on the Rasberry Pi website for doing a PXE boot with the slightly odd assumption
that it makes sense to use another Raspberry Pi as the server.   This may be a low cost option, but mostly I suspect
the reason people want to do PXE boots in the first place is to shorten the development loop by taking out the
need to flash an SD card or work natively on the RPI.  Thus they are much more likely to want to run the PXE server
and tftp / nfs servers on a development machine or a dedicated high performance server.

These intructions are also based on the assumption that you are using their default distribution, whereas I
prefer to do all my kernel developement in Arch Linux.

## Step 1, get it booting off an SD card

[archlinuxarm.org RPI 3 Instructions](https://archlinuxarm.org/platforms/armv8/broadcom/raspberry-pi-3)

This will mean you have all the elements needed to do a PXE boot as well.

### Add a few packages

This is from the [arch PXE boot instructions](https://wiki.archlinux.org/index.php/PXE)

Once booted and having done the usual 
''' pacman -Syu
to bring things up to date, install
