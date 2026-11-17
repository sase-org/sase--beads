# Bead: sase-1t2.13 — Boundary chaos test, crash convergence, and hand-off inventory guard

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.13` · **Size:** medium
**Created:** 2026-11-15 20:00:12 EST · **Closed:** 2026-11-17 04:59:25 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

chaos: a scripted fakey session (agent, sleep monitor, agent) that fires hijack at every checkpoint and requires HIJACKED, latched, or a defined redirect, never a generic refusal; crash-between-steps convergence tests; and a static guard test that fails when a new successor-launch path lacks a latch checkpoint.

## Notes

[2026-11-16T20:15:50Z · sase-1t2.8.1.land] CHECKPOINT INVENTORY (from sase-1t2.8.1 land, tree 8a1b84b096 + land fix) for the chaos static hand-off guard. Covered call sites:
(1) Spawn funnel agent/launch_spawn.py: refuse_if_latched(boundary="spawn") before process creation plus spawn_admission("spawn_callback") re-check under the target_index lock inside the claim callback; guard gets its recovery identity from bind_recovery_identity.
(2) turns/followup_launch.py::launch_turn_followup: refuse_if_latched("followup"), with HijackLatchedError re-raised ahead of the transfer, fresh-claim, pool-claim, and workspace-zero fallbacks. Its callers build guards with latch_guard_from_predecessor: gate_turn/followup.py and monitor/followup.py (monitor/resume.py -> launch_followup_agent goes through that same guard).
(3) agent/detached_child.py: two detached-child guards.
(4) axe/run_agent_exec_staged_dispatch.py: enforce_staged_adoption_latch under the adoption lock; enforce_adoption_replay_latch on the already-adopted, replay, and held paths; moot_runner_latch_at_run_end. Callers in axe/run_agent_exec.py (staged dispatch in setup and loop) re-raise HijackLatchedError.
(5) axe/run_agent_successor_inprocess.py: enforce_inprocess_successor_latch before member identity mutation.
(6) axe/run_agent_exec_pipe_handoff.py and axe/run_agent_successor_staged_identity.py: enforce_adoption_replay_latch (pipe replay and staged restoration).
(7) axe/run_agent_successor_delivery.py: check_detached_delivery_latch before submit, plus a guarded spawn via latch_guard_from_predecessor.
(8) Retry: axe/run_agent_exec_retry.py (in-process, check_retry_latch with re-raise) and axe/run_agent_retry_spawn.py (spawned, check plus re-raise so a refused spawn retry cannot fall into an in-process retry).
(9) axe/run_agent_exec_finalize.py: run-end moot plus observe_runner_latch, so finalize keeps applied-latch custody.
(10) ace/scheduler/_stale_running_hijack.py: reconcile_latched_records for dead owners.
Narrow exemptions:
(a) Launches with no predecessor (guard None) are unaffected by design.
(b) spawn_guard._authorized_recovery lets one launch through: the authorized hijack recovery successor, whose RECOVERY_LINEAGE_ENV hijack_id equals the record's hijack_id and whose record is in an applied state with latched_at set.
(c) refuse_if_latched ignores records for a different predecessor (artifacts_dir/member mismatch) and applied immediate (non-latch) records where latched_at is None. Those are owned by ordinary hijack custody, not the latch.

[2026-11-17T08:18:01Z · sase-1t2.11.1.7] MONITOR CANARY COUNTS from sase-1t2.11.1.7 land (for chaos inventory): continue path produces 1 hijack record and 1 same-workspace follow-up successor; rerun path produces 1 new monitor command in the held workspace and 1 eventual follow-up. Both fakey canaries passed on this tree. Does not take over crash/inventory work.

[2026-11-17T09:59:25Z · sase-1t2.13] chaos phase done: added tests/test_agent_hijack_chaos.py (536 lines, 11 tests). Boundary chaos covers staged/replay/inprocess/run-end-moot/retry/detached/spawn/followup checkpoints, each asserting HijackLatchedError or a defined moot verdict (never generic refusal) and at most one suppressed successor. Crash convergence kills the worker at record/intent/pin/begin_stop/terminate/settle/evidence/publish/latch-apply states and asserts stale-sweep/latch reconciliation converges with no second stop (target slot still maps to the one hijack id) and no surviving-writer release (dead owner settles held, live owner goes stop_blocked with custody retained). Static inventory guard enumerates every successor-launch primitive call site and requires a latch checkpoint or one-line allow-list reason. Verified: new file 11 passed standalone; sase tool run check 432a36725a555757ccfb55cf2964889c succeeded (all lint gates + scoped tests, exit 0). No epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1t2.10](sase-1t2.10.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.11](sase-1t2.11.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.14](sase-1t2.14.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.9](sase-1t2.9.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.13/README.md) | [sase-1t2.13](sase-1t2.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ab2401`](https://github.com/sase-org/sase/commit/9ab2401aea42479ef3eb56cd59035c2def910942) | test(hijack): add agent hijack chaos coverage | [sase-1t2.13](sase-1t2.13.md) | 2026-11-17 05:01:56 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check cross-epic coordination between hijack epic sase-1t2 and TUI perf epic sase-1t3 | 1 |
| read-by | [agent:sase-1t2.11.1.7][2] | Check whether canary recorded monitor checkpoint counts for chaos phase | 1 |
| read-by | [agent:toobig-9v.local_trust_management.0][3] | Check whether the boundary-chaos phase owns the oversized hijack action test file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.7/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9v.local_trust_management.0/README.md

<!-- sase:referenced-by:end -->
