---
tags:
  - leichfs
  - decisions
  - blocker
---

# Open Decisions

These are the missing pieces most likely to reconnect the old work. Answer each with a link, commit, test, or citation—not only a narrative statement.

## Project identity

- [ ] Is **LeichFS** the original system name? Find it in source code, Git history, documentation, or prior presentations.
- [ ] Where is the implementation repository, if any?
- [ ] Is the goal a new filesystem, a prototype exploring one improvement, or a comparison study?

## Threat model

- [ ] Who is the attacker: a person with the storage media, another local account, a backup/cloud provider, or a process on the unlocked user account?
- [ ] What must remain confidential: content, filenames, directory tree, file size, timestamps?
- [ ] Is authenticity/tamper detection required? What happens on detection?
- [ ] Which attacks are explicitly out of scope: memory capture, keylogger, malicious kernel/root, access-pattern leakage, rollback?

## Cryptographic format

- [ ] Which vetted AEAD construction/library API is used for file contents?
- [ ] How are nonces generated and made unique?
- [ ] What chunk size permits random access and how are partial writes handled?
- [ ] Is every chunk authenticated? How are file length and metadata authenticated?
- [ ] Are filenames encrypted, encoded, or left plaintext? What about long names?
- [ ] What exactly does libargon2 derive, with what algorithm variant, memory/time/parallelism parameters, salt, and upgrade policy?

## Filesystem semantics

- [ ] Which FUSE API and Linux distribution/version are actual targets? (`Linux Kernel 7.0+` in the template needs verification; it may be a placeholder or future target.)
- [ ] Which POSIX operations must work for the report’s scope?
- [ ] How do permissions, ownership, symlinks, extended attributes, hard links, and file locking behave?
- [ ] What is cached, how is it invalidated, and can plaintext persist in cache/memory?

## Evaluation commitment

- [ ] What is the baseline: unencrypted filesystem, gocryptfs, or both?
- [ ] What one outcome would count as success, and what result would falsify the hypothesis?
- [ ] What hardware, filesystem, storage device, OS, tool versions, and mount flags will be fixed and reported?

