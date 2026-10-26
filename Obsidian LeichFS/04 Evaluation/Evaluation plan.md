---
tags:
  - leichfs
  - evaluation
  - benchmarking
status: planned
---

# Evaluation Plan

## Goal

Measure the cost and behaviour of LeichFS in a reproducible environment. Compare like with like: the same device, underlying filesystem, dataset, cache condition, and mount configuration across all systems.

## Systems under test

1. **Plain baseline** — the backing filesystem/directory without encryption.
2. **gocryptfs baseline** — exact version and mount/configuration recorded.
3. **LeichFS** — exact commit/build/configuration recorded.

Do not present gocryptfs results until its configuration is documented; encryption options can materially affect results.

## Candidate workload matrix

| Dimension | Workloads to include | Metrics |
| --- | --- | --- |
| Sequential I/O | large-file read/write | throughput, CPU, latency |
| Random I/O | fixed-size random read/write | IOPS, latency percentiles, CPU |
| Metadata | create, stat, list, rename, delete many small files | elapsed time, ops/s |
| Mount lifecycle | mount, unlock, unmount/remount | elapsed time, success/failure behaviour |
| Memory/cache | cold versus warm repeat read | throughput/latency; cache condition documented |
| Correctness | round-trip, wrong password, tamper/corruption, interrupted operation | pass/fail with observed behaviour |

## Tools recorded by the template

- `fio`: I/O workload generation. Preserve the job files and raw outputs.
- `perf`: CPU and system-level counters. Record selected events and permission constraints.
- `hyperfine`: command-level repetition/timing for mount or metadata scripts.

These tools were listed in the unfinished LaTeX methodology; their actual prior use is not established.

## Reproducibility record

For every experiment, save a Markdown/CSV record containing:

- date, Git commit/hash, compiler and library versions;
- CPU, RAM, storage model, Linux/kernel, backing filesystem, mount options;
- dataset generator and dataset sizes/counts;
- command/job configuration, run count, cache-clearing policy (if any), and random seed;
- raw outputs, derived metrics, failures/exclusions, and the script used to plot results.

## Analysis rule

Report medians and variability across repeated runs, not only a single best result. Explain whether the main cost comes from FUSE transitions, crypto, I/O size, cache state, or another observed factor. A performance result without a stated workload is not interpretable.

See [[03 Design/Open decisions]] for the decisions required before this plan becomes a protocol.

