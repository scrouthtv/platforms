# Basic Setup for major passwords
Here's a little bit of background:

Golang's compiler comes in at around 500 MB but is capable of compiling for basically every os/arch combination:
 - Windows
 - Linux
 - BSD
 - Android
 - WebAssembly
 - ...

This works all fine up to a point where the programmer has to do "raw stuff" (syscalls, ioctl, CGO, ...).
Testing this stuff is very difficult.

My background is Windows/Linux, I have machines running both of these sittung around all over the place.

When I did the first cross-platform raw stuff, I'd send the darwin executables via whatsapp over to a friend who'd test them for me and answer me some days later.
This is an example of how *not* to do it.

So one day, I created a VM for all of these OSs and tried to put some advice together if anyone else wants to test cross-platform applications.

I'll only focus on command line testing.
