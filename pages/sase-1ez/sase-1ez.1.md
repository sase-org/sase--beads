# Bead: sase-1ez.1 — GC pause recorder, memory heartbeat, and app-instance identity

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.1` · **Size:** medium
**Created:** 2026-10-02 16:44:56 EDT · **Closed:** 2026-10-02 19:34:25 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

gc-telemetry: add a lock-free gc.callbacks recorder with collection-trigger tagging and a recent-collections ring. A daemon flush thread writes rate-capped tui_gc_pause rows and a 5-minute tui_memory_heartbeat (RSS, VmSwap, major faults, exact per-generation GC totals, pluggable extra fields). Also add a per-instance app ID and an exec-aware startup clock. Telemetry is never auto-installed under the ace testing harness.

## Notes

[2026-10-02T21:59:52Z · sase-1ez.1] PROPOSED FOLLOW-UP: add source_revision to tui_startup rows once a cheap revision source exists (git probe is a subprocess, rejected as non-cheap on the startup path; sase_version is recorded instead)

[2026-10-02T22:00:38Z · sase-1ez.1] VERIFIED (phase gc-telemetry): new gc_telemetry.py (lock-free gc.callbacks recorder, trigger tagging, 256-ring, bounded queue, daemon flush thread 60/min rate cap, 5-min heartbeat with RSS/VmSwap/faults/GC totals, app-instance ID, install/uninstall, harness no-auto-install) + exec-aware startup clock + ace_handler anchor + mount/teardown wiring + startup/agent-load record fields + runbook docs. 20 new tests pass; neighbors pass (startup_telemetry 4, stall_watchdog 18). just check: all lint gates green incl. mypy+symvision (run fbbc512792d8419613f877187df6fad3); test-scoped escalated to full suite via Justfile epic-symbol lines and was still running at handoff — joined to verify monitor. No --epic-symbol entries remain for sase-1ez.1; added sase-1ez.2/sase-1ez.4 entries for watchdog-truth/idle-gc-policy symbols.

[2026-10-02T23:34:04Z · sase-1ez.1--1] just check TIMED OUT (monitor rkey22zsygzj, 1h0m7s budget, exit -9, signal 15 at test-scoped stage line 774) — not a stage failure: all lint gates green incl. fmt/mypy/symvision/SASE validation; no failing test evidence in retained log. Bounded re-verification this turn: pytest test_gc_telemetry + test_startup_telemetry + test_stall_watchdog = 42 passed; ruff format+check clean; mypy clean on gc_telemetry.py. Timeout cause not compared against clean base tree (full-suite-length scoped selection exceeded monitor budget).

[2026-10-02T23:34:25Z · sase-1ez.1--1] VERIFIED (phase gc-telemetry): just check timed out at 1h in test-scoped stage with all lint gates green (no stage failure); bounded re-verification passed: 42 tests (gc_telemetry 20 + startup_telemetry 4 + stall_watchdog 18), ruff clean, mypy clean on gc_telemetry.py. No --epic-symbol entries remain for sase-1ez.1.

## Dependencies

- **Blocks:** [sase-1ez.2](sase-1ez.2.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.4](sase-1ez.4.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.1.md) | [sase-1ez.1](sase-1ez.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55eec1b`](https://github.com/sase-org/sase/commit/55eec1b986425e4e5f79eb105d7ec10170f17ec1) | feat(ace): add startup clock, GC telemetry and lifecycle instrumentation | [sase-1ez.1](sase-1ez.1.md) | 2026-10-02 19:36:40 EDT |
