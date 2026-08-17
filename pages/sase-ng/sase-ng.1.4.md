# Bead: sase-ng.1.4 — Retire the in-process launch body and fan-out dispatchers

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.4` · **Size:** medium
**Created:** 2026-08-17 15:16:51 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

launch_retire: delete `run_agent_launch_body`, `run_single_agent_launch_body`, the four fan-out dispatcher mixins, and `proc_callable` on `_submit_launch_proc`, then delete or re-point every test that reached them through the discarded callable.

## Dependencies

- **Depends on:** [sase-ng.1.1](sase-ng.1.1.md) ◐ · ⧖ 2026-08-17
- **Depends on:** [sase-ng.1.2](sase-ng.1.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-ng.1.5](sase-ng.1.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.4/README.md) | [sase-ng.1.4](sase-ng.1.4.md) | 0 |
