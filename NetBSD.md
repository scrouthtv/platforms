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

`git` does not work out of the box since the basic installation does not come with ssl certificates:
```
 # pkgin install mozilla-rootcerts
 # mozilla-rootcerts install
```
See https://reddit.com/r/NetBSD/comments/dveadk/ssl_errors_with_git_and_curl/.

Install `go` and call it using `go115` (or the version you installed) instead of simply `go`.
