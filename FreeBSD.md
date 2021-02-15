# FreeBSD

## Installation

Here is a walk in the park.
Download the iso from https://freebsd.org/where/ (I chose FreeBSD-*-RELEASE-amd64-dvd1.iso), create a vhd with at least 5 GB and boot it.
Click through the installation process and reboot.

## Setup
Neither `su` nor `sudo` nor `doas` are preinstalled so log in as root, install the package managment tool by calling `pkg` and install the required packages:
```
 # pkg install go git neovim
```

Relogin as your normal user and test the code.
