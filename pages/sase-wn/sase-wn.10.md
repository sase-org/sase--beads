# Bead: sase-wn.10 — Perf counters, budgets, and regression guardrails

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.10` · **Size:** medium
**Created:** 2026-09-04 12:11:18 EDT · **Closed:** 2026-09-05 17:34:21 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

perf-guardrails: land the counters that prove the wins (chop spawns/min and no-op ratio in lumberjack metrics, per-tick reload counters in ace), lock in import-time and spawn-rate budgets as tests, and update the perf runbook.

## Notes

[2026-09-05T12:26:37Z · sase-wn.10] perf-guardrails landed: lumberjack metrics.json now records chops_spawned, chops_no_op, chops_skipped{trigger,run_every,inhibited}, last-tick spawn/skip/no-op, spawn_rate_per_minute, and no_op_ratio; status.json mirrors last-tick load; sase axe status human view shows Chop load / Load (JSON wire unchanged). Ace auto-refresh emits refresh.auto_tick spans (surfaces_reloaded, axe_file_opens) on SASE_TUI_TRACE. Deterministic floors: tests/test_idle_cpu_diet_guardrails.py plus existing import-budget and zero-spawn idle-tick tests. Runbook: docs/perf_runbook.md Idle-host CPU diet. tui_perf memory rule 14 added via sase memory init. just check lint green; scoped tests escalated (core-identity-changed on LumberjackMetrics) and the wrapper SIGTERM-killed the full suite at ~99%. epic-symbols clean.

[2026-09-05T14:51:09Z · sase-wn.10--1] 2h just check-full timed out on SIGTERM during silent test-cost (Justfile line 674); lint/fmt/symvision/validation were green. This follow-up: epic-symbols still empty; 142 idle-guardrail/import-budget/trigger/status tests passed; 87 axe dashboard/status tests passed. Retrying check-full with a 5h budget after waiting for the sibling sase_20 suite-gate holder (test-cost is ~38k items, ~90m uncontended; 2h was not enough under contention).

[2026-09-05T20:24:31Z · sase-wn.10--2] PROPOSED FOLLOW-UP: check-full test-cost hang — 5h landing-gate timed out (SIGTERM) at silent Justfile:674 `test cost`. Cost lease pid 1399794 started 15:12:55Z and heartbeated through 17:14:26Z (progress 1396, ~2h1m of 5s-throttled calls), then no heartbeats for ~2h53m until monitor kill at 20:07Z; no cost recording written and the holder watchdog did not self-reclaim. Phase tests are not the hang: 165 idle-guardrail/import-budget/trigger/status/dashboard tests passed in 11.5s. just check selects 819 files (serial-budget-exceeded + missing coverage-context baseline) and can use the middle gear / fast lane; do not treat another silent test-cost hang as a phase product bug unless a named test fails.

[2026-09-05T20:48:39Z · sase-wn.10--3] just check flag-lint (rule 7: closed sase-wc still had v1_import_retired) was a stale workspace, not a phase defect: origin/master already removed the flag (sase-ws.4). Fast-forwarded this tree to origin/master and restored the uncommitted perf-guardrails work; regenerated sase/memory/README.md via sase memory init. Flag lint now passes. Phase tests after FF: 179 passed in 11.17s (idle-guardrail/import-budget/trigger/status/dashboard). select_tests escalates to the governed fast lane on core-identity-changed (core-cargo, environment-metadata, extension; 3523 files) — middle gear does not apply; this is not test-cost. Re-running just check next.

[2026-09-05T21:34:21Z · sase-wn.10--4] perf-guardrails verified and closed. Lint: all just check gates green (fmt python/markdown, keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, committed plans). just check PASSED scoped (819/3523 files, 23.2%; rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded; contexts baseline missing; gear 4 workers; 26m26s; exit 0). Idle-tick zero-spawn, import-budget, and status overlay covered by tests/test_idle_cpu_diet_guardrails.py plus axe lumberjack/status/dashboard tests (179 passed in 11.17s after origin/master FF). epic-symbols clean for sase-wn.10. Two prior just check-full hangs at silent test-cost (Justfile:674) are host/cost-plugin, not a phase failure; not re-run.

## Dependencies

- **Depends on:** [sase-wn.1](sase-wn.1.md) ✓ · ⧖ 2026-09-04
- **Depends on:** [sase-wn.3](sase-wn.3.md) ✓ · ⧖ 2026-09-04
- **Depends on:** [sase-wn.5](sase-wn.5.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wn.10.md) | [sase-wn.10](sase-wn.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ed0f11`](https://github.com/sase-org/sase/commit/9ed0f11b7c21c5da288833b44bfeb85ca12f16fc) | feat(axe): add idle-host perf counters, budgets, and status overlay | [sase-wn.10](sase-wn.10.md) | 2026-09-05 17:36:31 EDT |
