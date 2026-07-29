# Bead: sase-as.2 — Marks on non-PR Artifacts sub-tabs

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.2` · **Size:** medium
**Created:** 2026-07-29 14:31:01 UTC · **Closed:** 2026-07-29 15:38:39 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

subtab-marks: route `toggle_mark`/`clear_marks` on the Artifacts tab through the active sub-tab instead of the PR list, store marks per sub-tab keyed on the pane's existing stable entry target, render the mark glyph, and let the sub-tab copy menus copy a marked set.

## Notes

[2026-07-29T15:38:39Z · sase-as.2] Implemented stable-target marks for Commits, Plans, Chats, and Bugs; verified per-subtab toggle/clear isolation from PR marks, refresh-safe row glyphs, conditional footer counts, project-scope clearing, and marked-set copy formatting/count toasts. Focused Artifacts suites: 84 passed; final marking/copy plus Help visual rerun: 30 passed. just check passed every format/lint/mypy/Symvision/toobig gate, then stopped on pre-existing stale provider skills and missing prompt backlinks. Full suite: 23,622 passed, 7 skipped; Help golden updated and passes, leaving only 3 unrelated AXE description goldens whose expected images are incomplete/broken baselines.

[2026-07-29T15:39:37Z · sase-as.2] Verified focused Artifacts tests (84 passed), final marking/copy and Help visual checks (30 passed), full suite with 23,622 passed and 7 skipped apart from three unrelated AXE golden mismatches, plus formatting, Ruff, mypy, Symvision, and size gates.

## Dependencies

- **Depends on:** [sase-as.1](sase-as.1.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.2/README.md) | [sase-as.2](sase-as.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d867a44`](https://github.com/sase-org/sase/commit/d867a44ff21343d9a193f9480c46435f881ef5fd) | feat(ace): support marks across artifact panes | [sase-as.2](sase-as.2.md) | 2026-07-29 15:40:10 |
