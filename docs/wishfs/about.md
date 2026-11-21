---
title: About wishfs
description: What is wishfs and how is it structered
order: 1
---

**Wishfs** is a modified version of the [ouichefs](https://github.com/rgouicem/ouichefs) Linux filesystem. In the original implementation, individual file sizes are capped at 4 MB due to the design of the index block. Wishfs removes this limitation by introducing an extent-based storage layout to support virtually infinite file sizes, trading off storage capacity under heavy fragmentation and raw I/O performance.

This repository provides a reproducible build environment containing a preconfigured Linux kernel tree, the filesystem module, and utilities to generate and test disk images.

## Repository Structure
* `ouichefs` - Filesystem source code, test suites, and image-creation utilities (see directory for component licenses).
* `Makefile` - Main build orchestration for the kernel, filesystem tools, and test images.
* `tests` - bash scripts to setup the filesystem and C programs to test the I/O operations

