# Bead: sase-1eg.3 — Split panes with framed chrome and focus-scoped labels

[Bead Pages](../README.md) / [sase-1eg](README.md) / sase-1eg.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v1.md) · **Assignee:** `sase-1eg.3` · **Size:** medium
**Created:** 2026-10-01 15:39:35 EDT · **Closed:** 2026-10-01 18:46:25 EDT
**Plan:** [202610/pager\_split\_panes.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_split_panes.md)

## Description

split-panes: pure split model; `\` / `|` / ctrl+f / `+` / `-` keys; q, Esc and exhausted backspace close a pane; pane clone on split; link labels only in the focused pane; framed panes with the subject in the border title/subtitle and accent focus colors; split footer verbs, small-window guard, help rows, and async-safe pane teardown.

## Notes

[2026-10-01T22:45:34Z · sase-1eg.3] PROPOSED FOLLOW-UP: pager visual goldens drift on clean base (history/timeband/timeline_picker, 34 records) — time-based golden staleness, app single-pane goldens unchanged; refresh goldens in polish-docs phase

[2026-10-01T22:45:55Z · sase-1eg.3] PROPOSED FOLLOW-UP: add ACE modal test with Agents tab under pager modal proving backslash/pipe/ctrl+f split the pager while the Agents deck stays SINGLE

[2026-10-01T22:46:25Z · sase-1eg.3] split-panes implemented and verified: pure split model plus host wiring with framed chrome and focus-scoped labels; check green (ruff/mypy/symvision/test-waits/scoped 292 files incl. 9 model + 14 app pilot tests); pager visual shows only pre-existing time-based drift reproduced on clean base (app single-pane goldens unchanged)

## Dependencies

- **Depends on:** [sase-1eg.2](sase-1eg.2.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1eg.4](sase-1eg.4.md) ✓ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.3/README.md) | [sase-1eg.3](sase-1eg.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd32637`](https://github.com/sase-org/sase/commit/dd32637d2cb1e3e3ccfc2632dece9f2e3e1eb458) | feat(pager): split panes with framed chrome and focus-scoped labels | [sase-1eg.3](sase-1eg.3.md) | 2026-10-01 19:12:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eg.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1eg.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.land/README.md

<!-- sase:referenced-by:end -->
