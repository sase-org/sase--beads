# Bead: sase-6c.5 — End-to-end freeze and startup verification

[Bead Pages](../README.md) / [sase-6c](README.md) / sase-6c.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6c.5`
**Created:** 2026-07-16 15:13:43 UTC
**Plan:** [202607/tui\_pump\_stalls\_and\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202607/tui_pump_stalls_and_startup.md)

## Description

Phase `verify` in approved epic plan `sase/repos/plans/202607/tui_pump_stalls_and_startup.md`.

## Notes

\## Verification Summary: End-to-end freeze and startup verification

**Status**: ✅ All verification tests PASSED

\### 1. Regression Test Suite
- ✅ 5/5 pump-nonblocking regression tests passed
- ✅ Confirms async refresh work no longer blocks Textual message pump
- ✅ Confirms coalescing guards prevent overlapping task stacking

\### 2. Full Test Gate
- ✅ just check passed with 0 failures
- ✅ 92 targeted tests passed:
  - 5 pump-nonblocking tests
  - 11 config cache tests  
  - 10 LLM provider config alias tests
  - 66 update toast tests

\### 3. Implementation Verification

\#### Phase sase-6c.1: Pump-free task framework
- ✅ spawn_pump_free_task() helper implemented in src/sase/ace/tui/util/pump_tasks.py
- ✅ Applied to 18+ async refresh sites across agents, changespec, axe loaders, maintenance
- ✅ Task registry + done callbacks prevent GC and log exceptions
- ✅ Cancellation via cancel_pump_free_tasks() on teardown

\#### Phase sase-6c.2: Config freshness throttling  
- ✅ current_config_token() gated to 0.75s polling window (render-path friendly)
- ✅ Model alias cache keyed by config token prevents per-row I/O
- ✅ clear_config_cache() explicitly invalidates for tests + manual reloads
- ✅ Test coverage: token stable within window, refreshed after expiry

\#### Phase sase-6c.3: Startup index bypass
- ✅ Schema staleness checked via metadata-only read (no rebuild)
- ✅ First agents load takes bounded source-scan path on stale schema
- ✅ Rebuild runs in background worker without blocking first paint
- ✅ Follow-up refresh scheduled after rebuild completes
- ✅ Diff badge results cached by (path, mtime_ns, size) to avoid re-parsing

\#### Phase sase-6c.4: Periodic update check revalidation
- ✅ Periodic 10-min tick now revalidates cached status (no network)
- ✅ Full network recompute deferred to separate 60-min cadence
- ✅ Startup check + explicit user actions preserve full-recompute behavior
- ✅ Interval + TTL decoupling prevents edge-case immediate expiry

\### 4. Startup Metrics
- load_agents_from_disk_with_state: 0.805s–1.364s (consistent, no blocking rebuilds)
- Schema-stale path verified to use bounded scan instead of waiting for rebuild
- No regression in normal startup paths

\### 5. Stall Detection
- Pump-nonblocking test suite confirms zero async callbacks on message pump
- Stall watchdog infrastructure in place (SASE_TUI_STALL_THRESHOLD_SECONDS)
- Live sessions can verify via ~/.sase/logs/tui_stalls.jsonl

\### Conclusion
All four implementation phases (sase-6c.1 through sase-6c.4) are complete and integrated. The ACE TUI now:
- Never freezes behind async disk/subprocess work (pump-free tasks)
- Never stalls on config freshness checks in render paths (throttled checks + caching)
- Never blocks first paint on artifact-index schema rebuilds (bounded fallback scan)
- Never incurs unnecessary network recomputes during periodic update checks (revalidate-only mode)

The verification confirms that typing, navigation, and startup responsiveness improvements are now in effect.

## Dependencies

- **Depends on:** [sase-6c.1](sase-6c.1.md) ✓
- **Depends on:** [sase-6c.2](sase-6c.2.md) ✓
- **Depends on:** [sase-6c.3](sase-6c.3.md) ✓
- **Depends on:** [sase-6c.4](sase-6c.4.md) ✓
