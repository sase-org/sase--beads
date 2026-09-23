# Bead: sase-17a.1 — Phase 1: Two-panel Services sidebar with titled panels

[Bead Pages](../README.md) / [sase-17a](README.md) / sase-17a.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q5--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q5.md) · **Assignee:** `sase-17a.1` · **Size:** medium
**Created:** 2026-09-23 18:26:50 EDT · **Closed:** 2026-09-23 19:39:24 EDT
**Plan:** [202609/services\_tab\_panels.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_tab_panels.md)

## Description

service-panels: split the BgCmdList sidebar into statically composed Service Procs and Scheduled Routines panels over the unchanged global _axe_items index, with metadata titles, focus chrome, shared height allocation, width settling, scheduler-fold removal, docs, glossary strands, tests, and visual goldens.

## Notes

[2026-09-23T23:39:24Z · sase-17a.1--1] Phase 1 done: two-panel Services sidebar (Service Procs + Scheduled Routines) over reordered global _axe_items per design (procs, oneshots, routines). Verified: scoped fix-tui-screenshots clean (74/74 visual pass, 4 new services_panels goldens, Services-tab goldens current, zero Agents-tab PNG diffs); 7 visual tests re-keyed to new row order with index assertions; 83 phase unit tests pass; fmt-py/md, ruff, mypy, symvision green; full check's serial scoped suite showed zero failures to 94% with tail 10% re-run green. Epic-symbols clean for sase-17a.1; Justfile sase-17a.2 entry kept.

## Dependencies

- **Blocks:** [sase-17a.2](sase-17a.2.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17a.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17a.1.md) | [sase-17a.1](sase-17a.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3f5d34e`](https://github.com/sase-org/sase/commit/3f5d34e9fde31be2c0a8cc393f1db464e2cfa14d) | feat(axe): two-panel Services sidebar with titled panels | [sase-17a.1](sase-17a.1.md) | 2026-09-23 19:44:56 EDT |
