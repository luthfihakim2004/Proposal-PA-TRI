---
tags:
  - leichfs
  - gocryptfs
  - baseline
status: needs-source-verification
---

# gocryptfs and the Research Gap

## Recovered role

The original idea explicitly names **gocryptfs** as a modern “gold standard” encrypted FUSE filesystem and says it may still be improved. This makes gocryptfs the likely functional and performance baseline for LeichFS.

## What must not be assumed

No local source explains which gocryptfs limitation motivated LeichFS. Do not claim an improvement until it is tied to a source and an evaluation metric.

## Plausible directions to investigate — candidates, not recovered facts

| Possible focus | How to make it researchable |
| --- | --- |
| Performance | Compare defined workloads and explain the mechanism behind any improvement. |
| Usability | Compare setup, mounting, recovery, and error-handling steps with a task-based rubric. |
| Key handling | Specify a concrete key hierarchy/recovery model and analyse its trade-offs. |
| Metadata leakage | State exactly which metadata LeichFS protects better, and verify it by inspecting the backing store. |
| Caching | Measure latency/throughput and correctness under a stated cache policy. |

## Decision gate

Before the proposal calls LeichFS “better” than gocryptfs, record:

1. baseline version and configuration;
2. the one primary improvement target;
3. the metric(s), workloads, and acceptance criterion;
4. the security/usability cost of that choice.

That decision belongs in [[03 Design/Open decisions]] and should drive [[04 Evaluation/Evaluation plan]].

