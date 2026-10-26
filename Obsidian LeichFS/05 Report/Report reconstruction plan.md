---
tags:
  - leichfs
  - report
  - latex
---

# Report Reconstruction Plan

The existing report is structurally useful but substantively unfinished. Reuse its institutional formatting only after replacing all placeholder content.

## Existing LaTeX structure

| Location | Current state | Action |
| --- | --- | --- |
| `chapters/identitas.tex` | Has title, author, programme; supervisor fields are placeholders | Keep verified identity; fill formal fields |
| `chapters/abstrak.tex` | Placeholder text and keywords | Rewrite last, after results are known |
| `chapters/bab1.tex` | All narrative/aim/scope text is placeholder | Write from [[01 Project/Project Brief]] and verified sources |
| `chapters/bab2.tex` | Placeholder theory and dummy table/figure | Replace with FUSE, encrypted filesystem, crypto, key-management, baseline review |
| `chapters/bab3.tex` | Tool list and design section headings are useful clues; prose/tables are mostly placeholders | Replace with actual architecture, implementation, and protocol |
| `chapters/bab4.tex` | Generic schedule; wrongly mentions RL/MADDPG | Replace completely with real schedule or remove if not required |
| `bibliography/pustaka.bib` | Unrelated catalysis/materials references | Replace completely with real sources |
| `Proposal PA.pdf` | Generated template output | Do not treat as a research source |

## Suggested report outline

1. **Pendahuluan** — problem, gap, questions, goals, boundaries, report structure.
2. **Landasan Teori dan Tinjauan Pustaka** — FUSE, threat model, crypto concepts selected, gocryptfs and related work.
3. **Perancangan dan Implementasi LeichFS** — architecture, filesystem format, key flow, operations, caching, implementation environment.
4. **Metodologi dan Hasil Evaluasi** — evaluation protocol, correctness/security observations, benchmark results, limitations, discussion.
5. **Kesimpulan dan Saran** — answer each research question, constraints, future work. (Add a chapter only if the department format permits.)

## Writing sequence

1. Resolve the project/research decisions in [[03 Design/Open decisions]].
2. Build source-backed Chapter 2 notes first.
3. Document actual implementation while coding; do not reconstruct it from memory later.
4. Freeze and run the evaluation protocol in [[04 Evaluation/Evaluation plan]].
5. Write results/discussion, then introduction and abstract.

## Checklist before compiling a new draft

- [ ] No `\lipsum`, “Contoh”, “bla bla”, RL, or MADDPG remains.
- [ ] Every figure/table is LeichFS-specific, captioned, referenced, and sourced.
- [ ] Every claim about algorithms, FUSE, gocryptfs, or benchmarks has a credible citation or reproducible evidence.
- [ ] Bibliography has no template-era unrelated records.
- [ ] Report title and formal metadata are confirmed.

