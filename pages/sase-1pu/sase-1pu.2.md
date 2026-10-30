# Bead: sase-1pu.2 — Keep long-waiting bead agents alive when their dependency wakes (sase-12v)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.2` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

waiter-wake-recovery: reproduce the wake-time NameCollisionError after a long wait, identify the reservation or retry failure, and make the wake path recover or retry safely without launching duplicate successors. Preserve the original dependency and workspace state. Review the related sase-1el monitor-start report, but do not assume a shared root cause from the exception class alone.

## Notes

[2026-10-30T00:02:28Z · sase-1pu.2] Real-path replay evidence: an isolated registry-only stale owner is removed by the name-reservation load's staleness rebuild, and the refreshed bead waiter claims the same artifact identity; a rebuild containing a different live owner still raises NameCollisionError and leaves both artifact records intact. The historical sase-12v traceback remains unavailable, so this synthetic stale-owner case cannot be tied to the September 18 failure. The focused runner, registry, wait, bootstrap, handoff, and epic-launch modules pass (113 tests); repository check is still running.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.2.md) | [sase-1pu.2](sase-1pu.2.md) | 0 |
