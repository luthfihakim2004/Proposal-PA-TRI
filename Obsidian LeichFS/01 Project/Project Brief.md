---
aliases:
  - LeichFS
tags:
  - leichfs
  - proposal
status: recovered-draft
---

# Project Brief

## Working title

**Rancang Bangun Sistem Berkas Ruang Pengguna Terenkripsi Berbasis FUSE Untuk Pengamanan Pada Media Penyimpanan Data**

English working translation: *Design and Implementation of a FUSE-Based Encrypted User-Space Filesystem for Protecting Data Storage Media.*

## Problem statement

Data is valuable and needs protection. The original idea notes identify filesystem-level data handling and storage as an area needing additional safeguards. Whole-disk encryption (named examples: LUKS and BitLocker) is perceived as unsuitable for the target use case because it normally requires administrative privileges. The intended alternative is an encrypted FUSE filesystem that works transparently in user space.

## Proposed answer

Design and evaluate **LeichFS**, a user-space encrypted filesystem using FUSE. It should expose a usable mounted directory while storing protected ciphertext in a backing directory. The report should define exactly what is encrypted, how keys are handled, and what security and performance trade-offs result.

## Research objective — candidate wording

To design, implement, and evaluate a FUSE-based encrypted filesystem that can protect user files without administrator privileges, then compare its usability and performance characteristics with an established encrypted FUSE filesystem.

## Candidate research questions

1. How can an encrypted FUSE filesystem provide transparent file access for a non-privileged user?
2. Which cryptographic layout and key-management approach are appropriate for LeichFS’s stated threat model?
3. What overhead does LeichFS add to representative file operations compared with an unencrypted directory and [[02 Research/gocryptfs and the research gap|gocryptfs]]?
4. Does the stored backing directory avoid exposing plaintext contents and the metadata that the chosen design says it protects?

## What is known versus not known

Known: intended platform/toolchain evidence is recorded in [[Recovered evidence and confidence]].

Not known: actual LeichFS source location, implemented features, cipher/mode, filename-encryption scheme, metadata policy, threat model, and prior experiments. These must be recovered separately or decided anew; see [[03 Design/Open decisions]].

## Candidate scope boundary

In scope: a Linux user-space filesystem, protection of data at rest in its backing store, mount/unmount workflow, correct file operations, key/password handling, and measurable overhead.

Out of scope unless evidence says otherwise: kernel modifications, full-disk/OS encryption, remote synchronization, multi-user sharing, network access, and claims of defense against a compromised running user session.

## Links

- [[Recovered evidence and confidence]]
- [[03 Design/Architecture candidate]]
- [[04 Evaluation/Evaluation plan]]
- [[05 Report/Report reconstruction plan]]

