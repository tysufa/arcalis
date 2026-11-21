---
title: Testing
description: How to test wishfs
order: 6
---
1. **Boot the VM:** Launch the QEMU environment with your newly compiled kernel and disk images using the provided script on the host machine:
```sh
./qemu-run-externKernel.sh
```
*(This exposes the test disk image as `/dev/sdc` and mounts the shared project directory at `/share` inside the guest VM.)*

2. **Run the Test Suite:** Once logged into the VM, execute the test script located in `/share/run_tests.sh` (or run the commands manually) to load the module, mount the filesystem, and run the single-threaded, multi-threaded, and `ioctl` tests. (you can inspect and modify this script in `tests/run_tests.sh`) 
