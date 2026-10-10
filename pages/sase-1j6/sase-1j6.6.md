# Bead: sase-1j6.6 — Runner doorbell, scheduler job, and waiter safety

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.6` · **Size:** medium
**Created:** 2026-10-09 15:02:06 EDT · **Closed:** 2026-10-09 20:46:33 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

trigger: have the dying runner drop a stdlib doorbell, mark recovery pending, and silence its failure notification. Add the fs-triggered scheduler job that sweeps and submits the healer as a durable proc. Keep waiters and wait_checks correct while a recovery is in flight.

## Notes

[2026-10-10T00:46:00Z · sase-1j6.6] PROPOSED FOLLOW-UP: Add a decisions-web record for update-skew auto-restart design (at most once per lineage, pre-provider only) — skipped per epic auto-decision, needs a human-approved memory change

[2026-10-10T00:46:09Z · sase-1j6.6] PROPOSED FOLLOW-UP: Local .venv sase_core_rs wheel is stale (missing claim_auto_restart_ledger binding; content-layout wire schema 5 vs 7): 7 test_agent_auto_restart_healer + 10 test_agent_wait_watch failures reproduce identically on clean base; rebuild wheel via just install-venv/rust-install

[2026-10-10T00:46:13Z · sase-1j6.6] PROPOSED FOLLOW-UP: 9 just-check test-scoped failures reproduce identically on clean base (parser help sort, marker mutation/path audits x2, tui import budget, config schema spare_process_patterns, completion snapshot x2, build mutex groups 21v20, pypi lock path); the waits-lane membership failure was mine and is fixed

[2026-10-10T00:46:33Z · sase-1j6.6] Trigger phase done: stdlib-only runner doorbell (pending recovery + atomic drop before silent notification, import-firewall tested); agent_auto_restart scheduler job (10s waits lane, fs trigger, durable healer proc, settle/resurface) with docs/axe.md entry; waiter safety via ledger forward lookup (wait-watch, wait_checks terminal-blockers, runner identity deps). Verified: 15 new trigger tests + 37 chop-trigger tests pass; ruff/ruff-format/mypy clean; symvision reports fewer items than base; remaining just-check failures reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-1j6.5](sase-1j6.5.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.9](sase-1j6.9.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.6/README.md) | [sase-1j6.6](sase-1j6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cf84c0`](https://github.com/sase-org/sase/commit/6cf84c01cb781bf20680cf3b8639a3cebede20c1) | feat(auto-restart): implement trigger phase with runner doorbell, scheduler sweep, and waiter forwarding | [sase-1j6.6](sase-1j6.6.md) | 2026-10-09 20:48:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.6][1] | Need the phase scope and design file | 2 |
| read-by | [agent:toobig-7j.test_run_agent_runner_refresh.0--1][2] | need bead status to triage symvision epic-symbol failure vs split work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.6/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.toobig-7j.test_run_agent_runner_refresh.0.md

<!-- sase:referenced-by:end -->
