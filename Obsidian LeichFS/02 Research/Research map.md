---
tags:
  - leichfs
  - research
  - literature-review
---

# Research Map

The current folder contains no usable LeichFS literature. This map captures the minimum research threads needed to turn the recovered idea into a defensible report.

## Core topics to research

| Topic | Why it matters to LeichFS | Output needed |
| --- | --- | --- |
| FUSE architecture and permissions | Establishes what can run in user space and what the kernel/FUSE boundary does | Citation plus short theory section |
| Encrypted-filesystem design | Defines content, filename, directory, and metadata protection trade-offs | Design comparison table |
| gocryptfs | Named project baseline | Versioned feature/performance comparison |
| Cryptographic construction | Prevents vague or unsafe “AES encryption” claims | Justified algorithm/layout decision |
| Password and key derivation | Explains why libargon2 appears in the intended tooling | Key hierarchy and parameter choice |
| Integrity and tamper behavior | Encryption alone does not automatically provide authenticity | Threat-model and test statements |
| Benchmark method | Makes performance claims reproducible | Test matrix and raw-result format |

## Literature-review questions

1. What file-content encryption and authentication approach does the chosen baseline use?
2. Which metadata remains visible in common encrypted FUSE designs: filenames, file sizes, directory structure, timestamps, access patterns?
3. What does “no administrator privilege” mean for FUSE mounting on the target Linux distribution, and what permissions remain necessary?
4. How do page caching, FUSE context switches, and crypto block/chunk size affect small and large I/O?
5. Which existing design limitation is LeichFS actually trying to improve? The answer must be specific and testable.

## Minimum source set before writing Chapter 2

- Official FUSE documentation for the API/version used.
- Official gocryptfs documentation and source/release documentation for the exact comparison version.
- Primary documentation or an authoritative paper for every cryptographic primitive chosen.
- At least three peer-reviewed papers or theses on encrypted user-space filesystems / encrypted storage, selected for direct relevance.
- Official manuals for benchmark tools used (`fio`, `perf`, `hyperfine`).

## Anti-patterns to avoid

- Calling a system “secure” without declaring an attacker, assets, and residual leakage.
- Comparing against gocryptfs from memory or against an unversioned configuration.
- Treating LUKS/BitLocker as direct functional equivalents; whole-disk encryption and a mounted encrypted directory solve overlapping but different deployment problems.
- Replacing the unrelated template bibliography with uncited web claims.

See [[gocryptfs and the research gap]] and [[03 Design/Open decisions]].

