# Raspberry PI Password Recovery Steps

Lost your password? Happens. I discovered this after my first Pi was dormant for many years and of course, what once was memorable is not always so.

To begin the recovery process, first power down the RPI, and follow the steps below:

## Method 1

* Remove SD card.
* Enter SD card to a machine capable of mounting EXT4 partitions.
  * For OSX, you can install `brew cask install osxfuse && brew install ext4fuse`
* Modify the /etc/shadow file to reset the password to None by entering an * between the first and second colon.

## Method 2

**Assumes you have an outboard monitor and keyboard.**

* Remove SD card.
* Enter SD card to a machine.
* Browse the Recovery partition.
* Look for a file called `cmdline.txt`.
* At the end of this file, enter `init=/bin/sh`, save.
* Unmount the SD card from machine.
* Reenter card to RPI.
* Power up the PI.
* Now during the boot sequence, enter `passwd pi`
* Enter a new password.
* Remove SD card.
* Enter SD card to other machine.
* Remove `init=/bin/sh` from `cmdline.txt`.
* Remove SD card.
* Reenter SD card to RPI.
* Enjoy.
