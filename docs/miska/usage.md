---
title: Usage and Benchmarking
description: How to use the schedulers and benchmark them
order: 3
---

## Partial Switching (`SCX_OPS_SWITCH_PARTIAL`)

All schedulers in this repository are configured with the `SCX_OPS_SWITCH_PARTIAL` flag. This means the kernel continues scheduling standard processes with its default `EEVDF` scheduler unless a task explicitly opts into `sched_ext` (such as via `SCHED_EXT` scheduling policy).

You can either use the provided benchmark utility (`src/benchmark.c`) which explicitly opts in, or remove the `SCX_OPS_SWITCH_PARTIAL` flag from the scheduler source (not recommended, as system-wide lowest-PID scheduling can starve critical system processes).

## Running the Benchmark

1. Inside the VM, compile the benchmark program:
```bash
gcc /mnt/work/src/benchmark.c -o bench
```

2. Start your chosen scheduler :
```bash
sudo /mnt/work/linux-7.2.15/tools/sched_ext/build/bin/scx_ksched # replace scx_ksched by the scheduler you want to use
# or to keep control of the terminal and ignore the latency reports
sudo /mnt/work/linux-7.2.15/tools/sched_ext/build/bin/scx_ksched 2>/dev/null &
```

> You can use ctrl+z to get back the control of the terminal and execute the benchmark or other tasks

4. Run the benchmark and measure scheduling latency with `perf`:

```bash
perf sched record -- ./bench
perf sched latency -p
```

> **Note on Built-in Metrics:** While the schedulers print basic statistics (currently `average_delay`) to `stdout`, these metrics have not been fully validated—use `perf` for reliable measurements.

## Demo

Below is a walkthrough of setting up and running the repository using a precompiled kernel:

<img
  src="/img/docs/miska/miska_demo.gif"
  alt="demo of installation and setup gif"
  style="max-width: 1200; width: 100%; height: auto; border-radius: 8px;">
