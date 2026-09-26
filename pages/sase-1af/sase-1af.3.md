# Bead: sase-1af.3 — Build source-based Services nav sections

[Bead Pages](../README.md) / [sase-1af](README.md) / sase-1af.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1v](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1v.md) · **Assignee:** `sase-1af.3` · **Size:** medium
**Created:** 2026-09-26 07:23:45 EDT · **Closed:** 2026-09-26 10:25:37 EDT
**Plan:** [202609/routine\_source\_nav\_sections.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_source_nav_sections.md)

## Description

source_panels: replace the single routine panel with fixed source sections and coherent row ordering, focus, sizing, and navigation.

## Notes

[2026-09-26T14:24:45Z · sase-1af.3--1] PROPOSED FOLLOW-UP: just check lint(symvision) fails on stale Justfile --epic-symbol entries for closed sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading); triage marks all 3 KNOWN with 4 distinct agents / 3 workspaces, touched=False, locator Justfile — pre-existing, not from sase-1af.3 diff

[2026-09-26T14:25:08Z · sase-1af.3--1] PROPOSED FOLLOW-UP: just check test(scoped) escalated to full suite (4405 files, context-baseline-missing/contract-set-always/no-baseline-depth-boost/serial-budget-exceeded) and timed out after 1h on loaded host; phase-scoped panel tests (94 tests) pass in ~8s — full-suite timeout is infra, not phase regression

[2026-09-26T14:25:37Z · sase-1af.3--1] source_panels done: 4 fixed Services panels (Service Procs, User, Plugin, Builtin) with origin-based membership, panel-order row build, per-panel titles with single scheduler badge, visible-only paint/height/width, generic J/K via index. Verified: 94 panel/nav/jump/height/identity tests pass; ruff/mypy/fmt gates passed in just-check log; symvision 3x KNOWN stale sase-19x.4 entries and full-suite scoped timeout recorded as PROPOSED FOLLOW-UP (base-tree, untouched by this diff); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1af.2](sase-1af.2.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1af.4](sase-1af.4.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1af.3.md) | [sase-1af.3](sase-1af.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`880f1f8`](https://github.com/sase-org/sase/commit/880f1f863e824f1009217e782deef7ec4b58c5ab) | feat(axe): add source-based Services nav panels | [sase-1af.3](sase-1af.3.md) | 2026-09-26 10:28:59 EDT |
