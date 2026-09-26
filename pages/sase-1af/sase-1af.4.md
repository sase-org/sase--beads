# Bead: sase-1af.4 — Make dense builtin navigation calm and observable

[Bead Pages](../README.md) / [sase-1af](README.md) / sase-1af.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1v](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1v.md) · **Assignee:** `sase-1af.4` · **Size:** medium
**Created:** 2026-09-26 07:23:47 EDT · **Closed:** 2026-09-26 11:13:43 EDT
**Plan:** [202609/routine\_source\_nav\_sections.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_source_nav_sections.md)

## Description

density_polish: add cached health badges before default folding, then verify visual design, documentation, and layout.

## Notes

[2026-09-26T15:12:50Z · sase-1af.4] PROPOSED FOLLOW-UP: just check lint(symvision) fails on clean base from stale Justfile --epic-symbol entries for closed beads sase-19x.4 (x3) and sase-18i (x2); re-key or drop them

[2026-09-26T15:13:13Z · sase-1af.4] PROPOSED FOLLOW-UP: no Services PNG goldens at 120x40/100x30/narrow exist in-repo to inspect for density_polish visuals; run check-full screenshot stage or add goldens

[2026-09-26T15:13:43Z · sase-1af.4] density_polish done: per-routine !N health badge from cached snapshots (same failure/timeout/missing-script set as titles, shown on folded rows), ace.services.fold_builtin_routines:true with first-sight builtin fold gated on full-snapshot readiness, docs updated (ace.md/axe.md: 4 panels, source semantics, J/K, folding). Verified: 156 related tests pass; just fix clean; just check passes through mypy/ruff/fmt, symvision failure pre-exists identically on clean base (recorded as follow-up). No epic-symbols for this bead.

## Dependencies

- **Depends on:** [sase-1af.3](sase-1af.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1af.4/README.md) | [sase-1af.4](sase-1af.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd83d3e`](https://github.com/sase-org/sase/commit/bd83d3e6075770b58fd46d0c1e088fbde74bbced) | feat(axe): calm dense builtin navigation with health badges and first-sight folding | [sase-1af.4](sase-1af.4.md) | 2026-09-26 11:16:41 EDT |
