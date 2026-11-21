---
title: Prerequisites and Installation
description: What you need to build and use the project
order: 4
---

### Prerequisites
Ensure the following tools and packages are installed on your build machine:
* **Build toolchain:** GNU `make`, `gcc`, and standard Linux kernel compilation dependencies.
* **Disk & archive utilities:** `dd`, `xz`, `cp`, `mkfs.ext4`, and `tune2fs`.
* **Filesystem formatter:** The `mkfs.ouichefs` binary (automatically compiled when building `ouichefs` via `make`).

### Building the Project
Clone the repository and run `make` from the root directory to compile the kernel, build the `ouichefs` module/tools, and generate the default disk images (`test.img`, `myHome.img`, and `pnl-tp-2021.img`):

```sh
make
```
