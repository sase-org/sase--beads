# Bead: sase-1ez.2 — Make the stall watchdog report whole-process stops and exact totals

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.2` · **Size:** medium
**Created:** 2026-10-02 16:44:58 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

watchdog-truth: detect whole-process stops from the watchdog's own poll lateness, even when the beacon already ran. Add late/poll_lag_s/net_stall_seconds and gc-overlap attribution to hitch and recovery rows, and count rate-limited episodes and seconds into the heartbeat. Ship a tools/tui_freeze_report script that computes the de-duplicated frozen share and the GC share per app instance.

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.2/README.md) | [sase-1ez.2](sase-1ez.2.md) | 0 |
