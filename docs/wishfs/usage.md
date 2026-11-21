---
title: Usage and configuration
description: How to use and configure wishfs
order: 5
---

### Make Targets

Run these commands from the repository root:

* `make` — Builds the kernel, `ouichefs` module/tools, and all disk images.
* `make kernel` — Compiles the Linux kernel inside `linux-6.5.7`.
* `make ouichefs` — Builds the `ouichefs` kernel module and user-space utilities.
* `make clean` — Cleans kernel build artifacts and removes temporary disk images.

### Configurable Variables

You can override the following `Makefile` variables via the command line:

* `nproc` *(default: output of `nproc`)* — Number of parallel jobs passed to `make -j`.
* `kdir` *(default: `./linux-6.5.7`)* — Path to the Linux kernel source tree.
* `ouichefsdir` — Path to the `ouichefs` subproject directory.
* `test_disk`, `home_disk`, `boot_disk` — Custom filenames for the generated disk images.

### Build Examples

Build only the kernel using 8 parallel jobs:

```sh
make kernel nproc=8
```

Generate only the test disk image using `ouichefs/mkfs/mkfs.ouichefs`:

```sh
make test.img
```

Clean build files and temporary images:

```sh
make clean
```
