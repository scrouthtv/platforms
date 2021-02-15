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

## General tips

### Using vi
`vi` comes preinstalled as the default editor on many unix-y distributions.
Basic usage:
 - Once you open it, you're in normal mode. Naviagte using the arrow keys or hjkl.
 - Enter insert mode by pressing `i`. Change text by typing or using backspace. You *can not* delete new lines using backspace.
 - Leave insert mode by pressing `esc`. Exit `vi` by typing `:q` followed by enter in normal mode.
 - Delete an entire line in normal mode by typing `dd`.

### Documentation for Go
If you're using a lot of syscalls and such, you'll find a lot of them broken when switching architectures.
If not already done, [create platform-specific files](https://golang.org/pkg/go/build/#hdr-Build_Constraints).

Each of them should contain platform-specific constants and code.

The default `syscall` package is deprecated since Go 1.4. If you use `x/sys/unix`, the web documentation is only valid for unix.
See other documentation from any platform for any platform by using go doc:
```
GOOS=freebsd go doc x/sys/unix
```
