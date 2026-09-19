# Bead: sase-13i.1 — Publish one aggregate roster per disk apply

[Bead Pages](../README.md) / [sase-13i](README.md) / sase-13i.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ns](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ns.md) · **Assignee:** `sase-13i.1` · **Size:** medium
**Created:** 2026-09-19 10:43:12 EDT · **Closed:** 2026-09-19 12:21:24 EDT
**Plan:** [202609/epic\_tribe\_panel\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_tribe_panel_flicker.md)

## Description

atomic-roster-publication: merge the generation-stamped proc projection into the disk/cached roster before the single finalize, rebase if the generation moved during the worker, and cover the empty-disk plus live-projection regression.

## Notes

[2026-09-19T16:21:24Z · sase-13i.1] Disk apply now merges the captured proc projection before the single finalize: empty-disk + live epic proc-shell publishes @epic on the first and only finalize; a generation move between worker prep and UI commit rebases onto the latest projection; observer snapshots during _agents_loading bump generation without finalizing. just check green (lint + scoped tests, including test_proc_shell_selection_survives_refresh.py).

## Dependencies

- **Blocks:** [sase-13i.3](sase-13i.3.md) ◐ · ⧖ 2026-09-19
- **Blocks:** [sase-13i.4](sase-13i.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-13i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-13i.1/README.md) | [sase-13i.1](sase-13i.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9831ab6`](https://github.com/sase-org/sase/commit/9831ab623c039e3b90730aa30129f256328bf26f) | feat(tui): publish one aggregate Agents roster per disk apply | [sase-13i.1](sase-13i.1.md) | 2026-09-19 12:23:33 EDT |
