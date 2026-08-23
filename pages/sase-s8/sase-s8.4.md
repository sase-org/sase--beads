# Bead: sase-s8.4 — Documentation, help polish, and integrated verification

[Bead Pages](../README.md) / [sase-s8](README.md) / sase-s8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bd.md) · **Assignee:** `sase-s8.4` · **Size:** small
**Created:** 2026-08-23 07:39:41 EDT · **Closed:** 2026-08-23 10:38:17 EDT
**Plan:** [202608/agent\_wait\_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_wait_command.md)

## Description

docs: document the command and the monitor gate idiom, polish help text and examples, and verify the whole feature end to end with `just check-full`.

## Notes

[2026-08-23T14:37:50Z · sase-s8.4--1] PROPOSED FOLLOW-UP: Investigate test-cost budget regression; monitored just check-full passed 36312 tests but test-cost exceeded idle/wall/Textual budget tolerances in dt6qs6frtzr9.

[2026-08-23T14:38:17Z · sase-s8.4--1] Updated CLI, monitor, and family docs for sase agent wait; verified help output, focused wait CLI/watch/live tests, just check, live CLI smoke, and monitored just check-full functional tests (36312 passed, 12 skipped). just check-full exited 1 only because test-cost exceeded global budget tolerances; recorded PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-s8.3](sase-s8.3.md) ✓ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s8.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-s8.4.md) | [sase-s8.4](sase-s8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab73c84`](https://github.com/sase-org/sase/commit/ab73c8498d1ccbaef92391d672e134ced27bd321) | docs(agent): document agent wait command | [sase-s8.4](sase-s8.4.md) | 2026-08-23 10:39:36 EDT |
