# NetBSD

## Installation

Also pretty easy, get the iso from https://cdn.netbsd.org/pub/NetBSD/iso/9.1/ and start it.
Only problem during installation: `Shall we continue?` they actually make you select Yes.

I additionally installed the binary version of pkgin, set the keymap to de-iso, and created a non-root user.

Reboot.

## Setup

Their package manager works out of the box:
```
 # pkgin install git go
```
If you try to use `pkg_add`, it'll fail.
