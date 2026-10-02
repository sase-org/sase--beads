# Bead: sase-1ez.1 — GC pause recorder, memory heartbeat, and app-instance identity

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.1` · **Size:** medium
**Created:** 2026-10-02 16:44:56 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

gc-telemetry: add a lock-free gc.callbacks recorder with collection-trigger tagging and a recent-collections ring. A daemon flush thread writes rate-capped tui_gc_pause rows and a 5-minute tui_memory_heartbeat (RSS, VmSwap, major faults, exact per-generation GC totals, pluggable extra fields). Also add a per-instance app ID and an exec-aware startup clock. Telemetry is never auto-installed under the ace testing harness.

## Dependencies

- **Blocks:** [sase-1ez.2](sase-1ez.2.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.4](sase-1ez.4.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.1/README.md) | [sase-1ez.1](sase-1ez.1.md) | 0 |
