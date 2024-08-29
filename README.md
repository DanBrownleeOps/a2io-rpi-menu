

# a2io-rpi-menu
a2io-rpi-menu is an extension to Apple2-IO-RPi, and specifically the a2pico variant, found here:
https://github.com/tjboldt/Apple2-IO-RPi/tree/main/RaspberryPiPico

## What does it do?
In a nutshell it allows a small Linux server, usually a Raspberry Pi or Raspberry Pi Nano act as USB boot image server and file storage for the Apple II. In addition it allows the the Apple II to take advantage of the Raspberry Pi/Linux server via BASIC extensions. i.e -rpi.command and -shell. It also can behave as a time source for your Apple II.

## What is needed?
 - Apple II+ or Apple IIe
 - Small Linux host, i.e. RPi Nano
 - A2Pico
 - USB DC block adapter. Needed only if you intend to power the Linux host independently and not from the a2pico board.
 - OTG USB micro adapter to USB-A female
 - Micro SDHC card.

## Setup
Follow the instructions here to get the a2pico setup initially: https://github.com/tjboldt/Apple2-IO-RPi/blob/main/PicoSetup.md

After the a2pico is working as intended, you will need to get the Ciderpress Linux command line tools installed, they can be obtained here: https://github.com/fadden/ciderpress/tree/master/linux Specifically, you will need to get the "mdc" command working. The mdc command allows the script to retrieve the volume label from the disk ".po" image file.

Next you will want to populate the disks folder with some disk images you would like to serve from your Linux host. The images need to be in the .po format. ProDos ordered.

As root add the modified apple2driver.service to your /etc/systemd/system folder. Once placed, do a systemtemctl daemon-reload and finally, systemctl restart apple2driver do both with root privileges.

You can now start/reboot your Apple II and it should present a menu of your install disk images.

 

