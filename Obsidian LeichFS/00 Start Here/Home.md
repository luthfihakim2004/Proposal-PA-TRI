---
tags:
  - leichfs
  - index
  - project-recovery
---

# LeichFS Project Recovery

This vault reconstructs the current evidence for the final-project report **Rancang Bangun Sistem Berkas Ruang Pengguna Terenkripsi Berbasis FUSE Untuk Pengamanan Pada Media Penyimpanan Data**. It is designed as a restart point, not as a claim that the design is already final.

## The recovered thread

[[01 Project/Project Brief|LeichFS]] appears intended to be a user-space encrypted filesystem for Linux, built with FUSE. The motivation recorded in the original notes is to protect sensitive files without requiring administrator privileges, unlike whole-disk encryption such as LUKS or BitLocker. [[02 Research/gocryptfs and the research gap|gocryptfs]] is the named comparison baseline and is described as a “gold standard” that may still have room for improvement.

The report template also preserves the intended technical area: FUSE 3.10+, OpenSSL 3.0+, libargon2, C++20, and performance tools (`fio`, `perf`, `hyperfine`). That is strong evidence of the project’s direction, but **not evidence that any of those parts were implemented or benchmarked**.

## Start here

1. Read [[01 Project/Recovered evidence and confidence]] to separate facts from hypotheses.
2. Use [[01 Project/Project Brief]] to re-establish the proposal’s problem, goal, and scope.
3. Resolve the decisions in [[03 Design/Open decisions]] before writing detailed design or code.
4. Use [[04 Evaluation/Evaluation plan]] to decide what experiments the project must run.
5. Follow [[05 Report/Report reconstruction plan]] when resuming the LaTeX report.

## Map of content

- [[01 Project/Project Brief|Project brief]] — concise proposal draft.
- [[02 Research/Research map]] — literature and baseline questions.
- [[03 Design/Architecture candidate]] — a clearly labelled candidate architecture.
- [[04 Evaluation/Evaluation plan]] — reproducible performance and security evaluation plan.
- [[05 Report/Report reconstruction plan]] — what can be retained and what must be replaced in the existing report.
- [[06 Reference/Source inventory]] — every project file category inspected and what it contributed.

## Working conventions

- **Recorded** means it is explicitly present in a local source file.
- **Candidate** means a reasonable reconstruction, not a recovered fact.
- **Open** means it needs a decision, source check, or experiment before it goes into the report as fact.

> [!warning] Important
> The current `Proposal PA.pdf` and most `.tex` chapters are a report template populated with placeholder text. Do not cite their dummy tables, figures, bibliography entries, schedule, or prose as LeichFS research results.

