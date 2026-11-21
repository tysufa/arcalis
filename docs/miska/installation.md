---
title: Installation
description: How to install the schedulers
order: 2
---
## Compatibility

These schedulers have only been tested on **Linux kernel `7.2.15`**. While they should work on most kernels with `sched_ext` support, upstream API changes in newer or older kernel versions may cause compilation errors.

## Setup on NixOS

1. Enter the Nix development shell:
```bash
nix develop
```

2. Build the kernel, schedulers, and VM environment:
```bash
make
```

3. Boot the virtual machine using either the helper script or the generated NixOS VM binary:
```bash
./run
# or
./output-vm/bin/run-nixos-vm
```


> **Note:** `vm.nix` has only been tested on my local machine. If it does not work out of the box on your setup, feel free to adapt it or use your own VM.

## Setup on Other Linux Distributions

If you already have the required kernel and BPF build dependencies installed, run the following command to compile both the Linux kernel and the `sched_ext` schedulers:

```bash
make sched
```

You will need to configure and boot your own virtual machine or test environment separately.

