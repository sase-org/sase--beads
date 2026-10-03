# Bead: sase-1ez.2 — Make the stall watchdog report whole-process stops and exact totals

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.2` · **Size:** medium
**Created:** 2026-10-02 16:44:58 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

watchdog-truth: detect whole-process stops from the watchdog's own poll lateness, even when the beacon already ran. Add late/poll_lag_s/net_stall_seconds and gc-overlap attribution to hitch and recovery rows, and count rate-limited episodes and seconds into the heartbeat. Ship a tools/tui_freeze_report script that computes the de-duplicated frozen share and the GC share per app instance.

## Notes

[2026-10-03T00:16:48Z · sase-1ez.2] watchdog-truth verified: 49 passed (test_stall_watchdog 24 incl. 6 new late/overlap/totals/provider/instance-id tests, test_gc_telemetry 20 unchanged, test_tui_freeze_report_tool 5 new incl. mixed old/new-row fixture); sase bead epic-symbols clean; tools/tui_freeze_report --help + fixture runs OK; docs/perf_runbook.md documents new fields and report usage

[2026-10-03T00:29:57Z · sase-1ez.4] Phase sase-1ez.4 (idle-gc-policy, landed) now calls register_heartbeat_provider/unregister_heartbeat_provider from src/sase/ace/tui/util/gc_policy.py, so those two --epic-symbol lines were removed from the Justfile as symvision demands; sase-1ez.2(recent_collections) remains for watchdog-truth to consume.

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.2.md) | [sase-1ez.2](sase-1ez.2.md) | 0 |
