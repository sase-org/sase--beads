# Bead: sase-n7.4 — Take reconciliation off the synchronous load

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.4` · **Size:** medium
**Created:** 2026-08-16 11:17:42 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

off-read-path: remove the synchronous `_reconcile_dead_monitor_supervisors_for_tui()` call from `_load_agents_from_disk_impl` and run it in the background with a coalesced follow-up refresh, reusing the existing loader-cleanup shape, while preserving settlement semantics and preventing overlapping passes.

## Dependencies

- **Depends on:** [sase-n7.1](sase-n7.1.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n7.2](sase-n7.2.md) ◐ · ⧖ 2026-08-16
- **Depends on:** [sase-n7.3](sase-n7.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n7.5](sase-n7.5.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.4/README.md) | [sase-n7.4](sase-n7.4.md) | 0 |
