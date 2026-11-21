---
title: About Miska
description: What is the miska project.
order: 0
---

**Miska** is a collection of Linux `sched_ext` schedulers designed to prioritize tasks with lower Process IDs (PIDs). The repository includes four scheduler implementations:

* `scx_ksched` — A basic lowest-PID scheduler implemented primarily in the kernel via BPF.
* `scx_mine` — A basic lowest-PID scheduler implemented primarily in userspace.
* `scx_dyna` — A dynamic lowest-PID scheduler using active queues.
* `scx_kdyna` — A kernel-space dynamic scheduler using a cycle-weighted priority formula.

## Project Goals

The initial schedulers (`scx_ksched` and `scx_mine`) were built as a learning exercise in developing `sched_ext` schedulers, specifically to compare development ergonomics and runtime performance between kernel-space (BPF) and userspace scheduling. `scx_dyna` and `scx_kdyna` expand on this foundation with dynamic scheduling mechanisms.

