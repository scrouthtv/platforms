# DragonFly

## Installation

Again, it's all right there.
Download the iso from https://www.dragonflybsd.org/download/, start it. Log in as `installer`.
For simplicity's sake, I am using BIOS boot. All the defaults look very reasonable, so just enter through the installation process.

## Setup

Dragonfly's package managment system did *not* work out of the box for me. 
[You have to create a mirrorlist file](https://dragonflybsd.org/docs/howtos/HowToDPorts/#index2h2):

Create the file `/usr/local/etc/pkg/repos/df-latest.conf` (it must end in `.conf` which is a bit misleading in the docs) and enter only this text:
```
Avalon: {
    url             : http://mirror-master.dragonflybsd.org/dports/${ABI}/LATEST,
    enabled         : yes
}
```
The documentation suggests using a different mirror instead of the default one which seems to be chronically overloaded. All the mirrors I tested did not work at all, and I got up to 2 MB/s out of the default one, so it should be sufficient for just one or two packages.

Install all required packages like `pkg add go`.
