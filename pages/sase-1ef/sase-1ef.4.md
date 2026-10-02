# Bead: sase-1ef.4 — Timeline picker as an aligned table with open, now, and cursor markers

[Bead Pages](../README.md) / [sase-1ef](README.md) / sase-1ef.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v2.md) · **Assignee:** `sase-1ef.4` · **Size:** medium
**Created:** 2026-10-01 15:31:51 EDT · **Closed:** 2026-10-01 19:14:58 EDT
**Plan:** [202610/pager\_version\_clarity.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_version_clarity.md)

## Description

picker: turn picker rows into structured, column-aligned, never-wrapping rows; always list now; mark the open version separately from the cursor; preview what Enter and = will do; make comparisons always read older to newer.

## Notes

[2026-10-01T23:14:58Z · sase-1ef.4] Picker phase done: structured column-aligned non-wrapping rows with now-always-first, open (●) vs cursor (▸) markers, header pill + honest counts from the moment, live Enter/= footer preview with older-to-newer normalization (cursor-newer-than-open jumps with trail push). Verified: tests/memory/test_timeline_picker.py + tests/pager/test_history_timeline.py + tests/pager/test_app_history_timeline.py green (incl. new footer/normalization pilots), ruff + mypy clean, timeline_picker_* goldens regenerated + timeline_picker_many added and inspected; full just check delegated to verify monitor.

## Dependencies

- **Depends on:** [sase-1ef.2](sase-1ef.2.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1ef.5](sase-1ef.5.md) ✓ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ef.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ef.4.md) | [sase-1ef.4](sase-1ef.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a1fc3fc`](https://github.com/sase-org/sase/commit/a1fc3fc8e83fd3a4a3a959a90b0262ab4613335c) | fix(pager): privatize timeline picker helpers for symvision | [sase-1ef.4](sase-1ef.4.md) | 2026-10-01 19:45:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ef.4--2][1] | check bead status for final | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ef.4.md

<!-- sase:referenced-by:end -->
