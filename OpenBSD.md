# OpenBSD

## Installation

This one's a bit harder. Download the iso from https://openbsd.org/faq/faq4.html#Download. I got the `installXX.iso` for amd64 because it's ISO is the easiest for VirtualBox. I guess the img variant is better for qemu.

Create a VM (even with GO and some other things installed, the full installation (without X) comes in at just over 1 GB, so a vhd with less than 10 GB is sufficient.

Launch the VM and press enter all the way through the installer. If at some point it asks you to set up the network interface, the correct choice for me was `em0` and not `vlan0`.

Deselect all the x stuff during installation if you don't explicititly need it.

Remove the disk and reboot.

## Setup

The system really wants you to read your mail. If you do, exit using `exit`. Trust me, `q` does not do the trick.

Check if your internet connection works by `ping google.com` or comparable.
The default editor is `vi`, which is a bit weird for long-time modern vim users and must be haaaard for emacs users. 
Bad news for everyone, you have to use it once.

Choose a single mirror from https://www.openbsd.org/faq/faq15.html#Mirror and add it to `/etc/installurl` like this:
``` 
https://ftp.halifax.rwth-aachen.de/pub/OpenBSD/
```
There should not be any trailing folders after OpenBSD/.

Install git and go and optionally an editor for the 21st century:
```
pkg_add git go neovim
```

## Download your code and test it
```
 ~ git clone https://github.com/scrouthtv/termios
 ~ cd termios
 ~ go test .
```
