# Bead: sase-158.4 — Wire the live timeline into the sase update live path

[Bead Pages](../README.md) / [sase-158](README.md) / sase-158.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1d.md) · **Assignee:** `sase-158.4` · **Size:** medium
**Created:** 2026-09-21 07:49:31 EDT · **Closed:** 2026-09-21 12:25:50 EDT
**Plan:** [202609/sase\_update\_live\_progress.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress.md)

## Description

wire-live-update: add the -v/--verbose flag and renderer selection, declare the step timeline, run the managed uv upgrade as a streamed step with live package rows, add restart and completion rows, print the final frame and a deduplicated summary, expand output on failure, handle Ctrl-C with exit 130, and add log_path to the JSON output.

## Notes

[2026-09-21T16:24:47Z · sase-158.4] PROPOSED FOLLOW-UP: split tests/test_detach_scope.py (1231 lines, over the 1000-line toobig limit) so just check goes green

[2026-09-21T16:25:50Z · sase-158.4] wire-live-update done: -v flag, session wiring with inspect/managed/restart/completions steps, managed pkg rows, timeline_shown dedup, failure Full-log lines, Ctrl-C 130 with interrupted journal, log_path in JSON; 8 new tests pass, 422 area tests pass, lint gates fixed except pre-existing toobig in untouched tests/test_detach_scope.py (filed as follow-up)

## Dependencies

- **Depends on:** [sase-158.3](sase-158.3.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-158.5](sase-158.5.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.4/README.md) | [sase-158.4](sase-158.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f64bd3a`](https://github.com/sase-org/sase/commit/f64bd3ac23c282e3af056ace496b5def2eccf37c) | feat(update): wire live-update progress session timeline | [sase-158.4](sase-158.4.md) | 2026-09-21 13:32:15 EDT |
