# Purpose

This package provides a simple way to permanently get rid of snapd on Ubuntu
systems without breaking your system dependencies (ie `ubuntu-server-minimal`).


# Motivation

Freshly installed Ubuntu systems (ie 24.04 LTS) have the abominable Snap
packaging system included.

To really ensure their users can't remove it, Canonical even included it
in the dependency list of their metapackages.

Well, enough is enough.

So this project solves that particular problem.


# Usage

Stop any running instances of snap (you'll want to remove any downloaded
snaps first):

```
$ sudo systemctl stop snapd snapd.socket
```

Then install this package:

```
$ sudo apt install ./snapd-empty.deb
```

This will automatically remove snapd as it does so, and it *won't* break
your system dependency chains in doing so.  apt should continue functioning
as per normal afterwards.
