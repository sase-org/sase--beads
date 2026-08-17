# Bead: sase-ng.1.3 — Retire the cleanup worker bodies and their proc\_callable seam

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.3` · **Size:** medium
**Created:** 2026-08-17 15:16:51 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

cleanup_retire: delete the dead `_worker` closures behind kill, dismiss, and save persistence, drop `proc_callable` from `_submit_cleanup_proc`, and re-point the shared cleanup test harness at the durable persist-cleanup payload seam.

## Dependencies

- **Blocks:** [sase-ng.1.6](sase-ng.1.6.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.3/README.md) | [sase-ng.1.3](sase-ng.1.3.md) | 0 |
