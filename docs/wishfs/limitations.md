---
title: Known limitations
description: What are the drawbacks of wishfs
order: 3
---

* **Reduced I/O Performance (No Page Cache):** Because Wishfs relies on custom `read` and `write` implementations, file operations bypass the Linux kernel's page cache, significantly limiting read/write throughput.
* **Worst-Case Fragmentation Cap (2 MB):** Storing both a starting block number and a length doubles the size of each entry in the index block, halving the maximum number of entries it can hold. In the worst-case scenario where every extent is only 1 block long the maximum file size drops to half of the original `ouichefs` limit, capping out at **2 MB**.

