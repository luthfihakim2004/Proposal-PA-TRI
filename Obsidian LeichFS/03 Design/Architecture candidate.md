---
tags:
  - leichfs
  - architecture
  - candidate-design
status: candidate-not-recovered
---

# Architecture Candidate

> [!caution] Candidate reconstruction
> This page proposes a conventional design consistent with the title and intended toolchain. It is **not** evidence of the original LeichFS implementation.

## Conceptual flow

```text
Application
    ↓ POSIX file operation
Mounted plaintext view (FUSE mountpoint)
    ↓ FUSE callbacks
LeichFS userspace daemon
    ├─ path / filename transform
    ├─ content encrypt/decrypt + authenticate
    ├─ key manager
    └─ cache policy
    ↓ protected bytes / encrypted names
Ciphertext backing directory
```

## Candidate components

| Component | Responsibility | Decision still required |
| --- | --- | --- |
| FUSE adapter | Maps POSIX callbacks to LeichFS operations | High-level vs low-level FUSE API; required operations |
| Virtual namespace | Resolves plaintext paths and directory listings | Filename encryption, long names, collisions |
| Content layer | Encrypts/decrypts file chunks | AEAD scheme, nonce scheme, chunk size, sparse files |
| Key manager | Turns user secret into filesystem keys | Argon2 parameters, salt storage, key wrapping, unlock flow |
| Metadata layer | Stores configuration and per-file state | What is authenticated/encrypted; rollback/tamper behaviour |
| Cache layer | Reduces repeat work without breaking coherence | Caching scope, eviction, plaintext exposure in memory |
| Error/lock layer | Handles bad password, corruption, concurrent access, clean unmount | Failure semantics and logging policy |

## Candidate key hierarchy

```text
User password
    ↓ Argon2id (salt + recorded parameters)
Key-encryption key
    ↓ unwrap / verify
Random filesystem master key
    ├─ content-encryption subkeys
    └─ filename/metadata subkeys
```

Use independent subkeys and authenticated encryption only if that construction is supported by the selected library and justified with references. The exact algorithms and file-format version must be documented before implementation.

## Minimum correctness cases

- create, read, overwrite, append, truncate, rename, delete, mkdir, rmdir, and directory listing;
- unmount/remount and wrong-password behaviour;
- binary files, empty files, large files, and filenames with Unicode/special characters;
- interrupted write and corrupted/tampered backing-file behaviour;
- two operations on the same file, with documented concurrency semantics.

## Cross-links

- [[Open decisions]]
- [[04 Evaluation/Evaluation plan]]
- [[02 Research/Research map]]

