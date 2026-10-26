---
tags:
  - leichfs
  - evidence
  - project-recovery
---

# Recovered Evidence and Confidence

## Directly recorded in `IDEAS`

- Data has an important role; security is therefore crucial.
- Filesystems manage and store data, and need additional security.
- LUKS and BitLocker are named examples of disk encryption that require administrative privileges.
- Encrypted FUSE filesystems are described as secure, transparent, flexible, and usable without administrator privileges.
- gocryptfs is identified as a modern “gold standard” baseline, with possible areas to improve.

Confidence: **high**. These are paraphrases of the local `IDEAS` file, not new claims.

## Directly recorded in LaTeX project metadata

- The report title specifies a FUSE-based encrypted user-space filesystem for protecting data storage media.
- The report owner is Luthfi Hakim, 22/503361/SV/21499, Teknologi Rekayasa Internet, UGM.
- The methodology template lists Linux Kernel 7.0+, FUSE 3.10+, OpenSSL 3.0+, libargon2, C++20, Neovim, Git, CMake, `perf`, `fio`, and `hyperfine`.
- The unfinished system-design outline has headings for overall architecture, internal modules, filesystem layout, cryptographic flow, key management, caching design, and data collection.

Confidence: **high** that these items were written into the template; **medium** that every listed dependency was part of the intended final system; **low** that any was actually used successfully.

## Negative evidence — just as important

- Chapters 1–4, abstract, tables, figures, and most text use `\lipsum` or generic examples.
- The bibliography contains unrelated catalysis/materials-science references; it cannot support a LeichFS report.
- The schedule refers to RL/MADDPG and is unrelated to LeichFS.
- The PDF is a generated copy of the template, with no LeichFS results beyond title/identity/tool-list clues.
- No LeichFS implementation, experiment dataset, source-code repository, research PDFs, or genuine citations are present in this folder.

Confidence: **high**, based on the local source inventory.

## Safe conclusion

There is a coherent **project concept** but not a recoverable implementation or completed research report in this directory. The most defensible restart is to treat the notes as a new research plan anchored in the original concept, rather than trying to recreate undocumented results.

## Next recovery search

Search likely locations outside this folder for repositories/directories named `LeichFS`, `leichfs`, `fuse`, `gocryptfs`, `.git`, benchmark CSVs, shell history, and paper PDFs. If code is found, use [[03 Design/Architecture candidate]] only as a comparison lens, not as a description of the implementation.

