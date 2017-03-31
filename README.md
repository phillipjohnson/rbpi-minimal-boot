# Raspberry Pi Minimal Boot
The files in this project are the minimum required files for a Raspberry Pi to boot a linux kernel. This is useful if you want to quickly get your own kernel up and running without first downloading and installing something like NOOBS or Raspbian. It is *not* an alternative to either of those software!

## Getting Started
1. Put a blank SD card into your computer
2. Copy all of the files in the "boot" directory of this project onto the SD card
3. (Optional) Replace kernel.img with your own kernel
4. (Optional) Edit cmdline.txt with command line parameters that need to be passed to the kernel
5. Eject the SD card, pop it into yor Raspberry Pi and turn on the power

**Note:** Feel free to use the included kernel.img as a starting point, but all it does is alternately flash the PWR and ACT LEDs on a Raspberry Pi B+. (It likely will not do anything visibly noticeable on other models due to changes in the GPIO.)

## What do the files do?
(Adapted from [eLinux](http://elinux.org/RPi_Software) wiki)

 - **bootcode.bin**: This is used to retrieve the GPU firmware from the SD card, program the firmware, then start the GPU.
 - **cmdline.txt**: File for passing arguments to the Linux kernel
 - **kernel.img**: The linux kernel to run
 - **start.elf**: Once loaded, this allows the GPU to start up the CPU.

## Why?
All the tutorials I was finding online suggested starting with a linux distribution, even if I didn't want to actually *use* the Rasberry Pi as a linux box. In my case, I wanted to get started with the [Baking Pi](http://www.cl.cam.ac.uk/projects/raspberrypi/tutorials/os/) tutorials, but they assume you have one of the pre-loaded SD cards.
