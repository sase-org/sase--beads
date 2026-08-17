# Bead: sase-ng.1.1 — Restore forced name reuse on the durable launch path

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.1` · **Size:** medium
**Created:** 2026-08-17 15:16:50 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

force_reuse: extract the `%id:!name` force-reuse launch pipeline out of the orphaned TUI body into a shared `sase.agent.force_reuse_launch` module, carry ACE's confirmation through the `RUN_LAUNCH` request payload, and consume it in the `sase run` child so kill-and-edit relaunches work again before the orphaned copy is deleted.

## Dependencies

- **Blocks:** [sase-ng.1.4](sase-ng.1.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.1/README.md) | [sase-ng.1.1](sase-ng.1.1.md) | 0 |
