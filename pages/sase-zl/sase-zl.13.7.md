# Bead: sase-zl.13.7 — Repair real host-finalizer recovery and receipts

[Bead Pages](../README.md) / [sase-zl.13](sase-zl.13.md) / sase-zl.13.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zl.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zl.land.md) · **Assignee:** `sase-zl.13.7` · **Size:** medium
**Created:** 2026-09-11 23:43:32 EDT · **Closed:** 2026-09-12 07:10:57 EDT
**Plan:** [202609/monitor\_continuation\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_continuation_landing_repairs.md)

## Description

completion: repair recovery launcher arguments, serialize host adoption, and verify all finalizer actions with real controller and multi-repository receipt coverage.

## Notes

[2026-09-12T11:10:57Z · sase-zl.13.7] Host-completion recovery now calls the production follow-up launcher with the required keyword-only arguments (monitor_state, exit_code, elapsed_seconds, capture, project_name); a two-argument callback TypeErrors instead of hiding the integration bug. Host delivery adopts pending→reserved→acknowledged under one delivery-store lock with original workspace ownership and no degraded fallback.

Receipt completeness requires every declared commit repo (ok + sha) and later finalizer instances independently; a single successful receipt no longer finishes. Real controller/declaration adapters over patched dirty repos and fake stitch: eligible success uses zero provider.invoke calls and actually submits the prepared declaration. Stale fingerprint, missing check-full stages, unsupported executors, and post-finalizer tree drift each launch one recovery. Two-repository crash after the first stitch retains the ok receipt and never marks completed. Bead-action keep/close is required on commit decisions when assigned_bead is present (sase-zq.1).

Verified: pytest tests/monitor/test_monitor_host_completion.py tests/monitor/test_monitor_host_completion_controller.py (15 passed). just check lint gates (ruff/mypy/symvision/toobig) passed. test-scoped escalated to the full suite because src/sase/core/finalizer_facade.py gained validate_finalizer_bead_decision; 40903 passed, 4 failed (fakey timeout; propose_report python3 list-subscript). Isolated rerun of those four tests passed. sase bead epic-symbols sase-zl.13.7: no leftovers.

## Dependencies

- **Depends on:** [sase-zl.13.6](sase-zl.13.6.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zl.13.9](sase-zl.13.9.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zl.13.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zl.13.7/README.md) | [sase-zl.13.7](sase-zl.13.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ce8056`](https://github.com/sase-org/sase/commit/7ce80566f5193e5d903e6ca240b13d3e30fe954d) | feat(monitor): repair host-finalizer recovery and receipts | [sase-zl.13.7](sase-zl.13.7.md) | 2026-09-12 07:12:34 EDT |
