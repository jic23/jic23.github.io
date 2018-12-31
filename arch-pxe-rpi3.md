# PXE Booting a Raspberry Pi 3 with Arch

There are detailed instructions on the Rasberry Pi website for doing a PXE boot with the slightly odd assumption
that it makes sense to use another Raspberry Pi as the server.   This may be a low cost option, but mostly I suspect
the reason people want to do PXE boots in the first place is to shorten the development loop by taking out the
need to flash an SD card or work natively on the RPI.

## Step 1, get it booting off an SD card

[archlinuxarm.org RPI 3 Instructions](https://archlinuxarm.org/platforms/armv8/broadcom/raspberry-pi-3)

This will mean you have all the elements needed to do a PXE boot as well.

### Add a few packages

This is from the [arch PXE boot instructions](https://wiki.archlinux.org/index.php/PXE)

Once booted and having done the usual 
''' pacman -Syu
to bring things up to date, install
