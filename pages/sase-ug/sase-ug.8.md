# Bead: sase-ug.8 — Walking back across surfaces

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.8` · **Size:** medium
**Created:** 2026-08-26 14:48:29 EDT · **Closed:** 2026-08-27 01:02:46 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

trail: add the app-level link trail and breadcrumb so `Ctrl+O`/`Ctrl+Shift+O` walk link hops across tabs and restore what a forward hop changed.

## Notes

[2026-08-27T05:02:46Z · sase-ug.8--1] just check clean (fmt/ruff/mypy/keep-sorted/feature-flags/pyscripts/test-waits/changelog/patch-stitch/symvision/toobig/SASE-validation/committed-plans all passed, plus diff-scoped test lane green); 33 new/updated tests cover back/forward walk across artifacts/agents/axe tabs, per-tab query/project-scope restore, and breadcrumb rendering in the link rail.

[2026-08-27T05:03:09Z · sase-ug.8--1] PROPOSED FOLLOW-UP: back/forward walk restores query and project scope on the axe tab, but not AXE fold-expansion state, because the current codebase has no fold-expansion mechanism triggered by link-follow to restore. Land agent should decide whether this gap needs a follow-up bead.

## Dependencies

- **Blocks:** [sase-ug.10](sase-ug.10.md) ◐ · ⧖ 2026-08-26
- **Depends on:** [sase-ug.7](sase-ug.7.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ug.8.md) | [sase-ug.8](sase-ug.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d8e8b5a`](https://github.com/sase-org/sase/commit/d8e8b5ab8ed264a983fd892b29d8e6f752428a93) | feat(tui): add app-level link trail for Ctrl+O/Ctrl+Shift+O across tabs | [sase-ug.8](sase-ug.8.md) | 2026-08-27 01:04:08 EDT |
