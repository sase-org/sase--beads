# Bead: sase-1tc.3.1 — Resume interrupted chop launch batches without duplicates

[Bead Pages](../README.md) / [sase-1tc.3](sase-1tc.3.md) / sase-1tc.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) · **Assignee:** `sase-1tc.3.1.land`
**Created:** 2026-11-17 19:16:08 EST · **Closed:** 2026-11-19 05:22:57 EST
**Plan:** [202611/chop\_launch\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_launch_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/chop_launch_recovery.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/chop_launch_recovery.md

<!-- sase:links:end -->

## Description

Scheduler and service-host stops preserve every accepted chop launch, resume its original identities once, and respect explicit clan cancellation.

## Notes

[2026-11-18T12:14:52Z · sase-1tc.3.1.land] LANDER FOLLOW-UP TRIAGE (sase-1tc.3.1.land): (1) sase-1tc.3.1.1 note #2 stale TUI import-budget cap — DECLINED, obsolete: tests/ace/tui/test_app_import_budget.py passes on current master 07479640e2 (11 passed), so no task. (2) sase-1tc.3.1.1 note #3 sase-core clippy manual_range_patterns at audit_query.rs:257 — DECLINED, obsolete: sase-core 9f9341e5 (on master, below the pin 71c59dca) rewrote the pattern to 1..=3. (3) sase-1tc.3.1.2 note #1 parallel-only PromptTextArea text-area--gutter KeyError in test_prompt_bar_hot_spare.py::test_each_activation_mints_new_session — corroborated via /sase_new_task as a +1 on existing flake task sase-1q8 (same file, same load-only full-lane mode), with ref file:explicit:b5e36a4c8108159a2d2d821e; not caused by this epic. No new task beads created.

[2026-11-18T12:17:18Z · sase-1tc.3.1.land] LANDING VERIFICATION (sase-1tc.3.1.land): all 5 phases closed. Commits c6b6da1d2c, 558fbd127f, 3cf982bdff, b8c9f6c6aa, 07479640e2 are on master; sase-core 6cd9a0c2 is below the pin 71c59dca. Rust contract and bindings are sound. Integration drift since c6b6da1d2c: 10 non-epic commits (video/viewer, artifact-read audit, bead stranded snapshot, workflow_runner split touching run_agent_exec.py imports only, keymap test split, log retention). None touches chop launch, kill, or lifecycle code, so no integration edits were needed. NOT CLOSABLE: two independent reviews plus my own reading confirmed epic-caused defects. (1) collect_spawn_observations matches member agent_name against _ChopAgentRecord.cl_name, which is the project name or VCS ref in production. Spawn-before-ack members are therefore never matched_spawn, visible names become reservation_only and relaunch, and foreign_conflict/live_owner are never emitted. The acceptance harness and unit test faked cl_name=agent_name, so the sase-1tc.3 TASK RESOLVED evidence rests on an impossible evidence shape. (2) Replay omits build_chop_launch_env, origin=generated, the stored clan_generation, wait rewiring, and the run-history merge. (3) The first-run executor never takes batch ownership, so a routine/manual race can double-dispatch. (4) A clan kill crossing a launch makes the run action_failed (Rust rejects acknowledge on a cancelled batch), on both the ordinary and typed paths. (5) Typed dispatch ignores outer cancellation. (6) The launch-exception path releases once-per claims for members the retained journal replays. (7) The lifecycle runner only waits for paused, not open. (8) Recovery holds and errors are swallowed or silent. (9) Manifests never retire, and the 256 cap applies before filtering. (10) TUI panel kills skip cancellation, and _batch_clan returns only the first clan. (11) Notices lack episode identity and delivery durability. Planned as child epic plan sase_plan_chop_recovery_defects (phases evidence -> ownership -> visibility -> acceptance, parent_bead sase-1tc.3.1). Its lander resumes this landing. Epic-symbol entries (19, all keyed to sase-1tc.3.1) stay in place until that resumed close.

[2026-11-18T22:10:35Z · sase-1tc.3.1.6.land] Closeout blocker (from sase-1tc.3.1.6 tale closeout): child epic sase-1tc.3.1.6 is closed with four repairs verified (strict observations, scoped generation + Rust match, read-only dry-run, dead-executor settlement via SettleCancelledDispatch). Parent close deferred: 15 epic-symbol entries for sase-1tc.3.1 remain whitelisted in Justfile. Inspection shows module-attribute consumers (chop_batch_store.X) but symvision requires direct from-imports to drop the whitelist; removing the 15 rows fails symvision with 15 unused-public reports. Needs follow-up refactor to direct-import the 15 symbols (or privatize/pragma) then re-run just symvision before normal close. Full just check (ToolRun eb35e3f1fb3f7b73a2c615c92ac725ab) is still running after rebuilding sase_core_rs with new bindings; focused suites green (Python 46 passed, lifecycle 29 passed, Rust 14+14 passed). Do not force-close.

[2026-11-18T23:54:19Z · toobig-a6.test_projected_detail_retention.0] DISCOVERED ISSUE: While splitting tests/ace/tui/models/test_projected_detail_retention.py, standalone `just _lint-mypy` reproducibly failed at `src/sase/axe/_chop_batch_recovery_observations.py:85`: argument 2 to `_name_in_blocked_roots` is `Mapping[str, Any] | set[str]`, while the helper expects `Mapping[str, Any]`. The requested `sase tool run check` (ToolRun e605bb0f7df08f628804aed3ff3e7607) stopped at this NEW mypy failure. Standalone `just _lint-toobig` also reported `tests/axe/test_axe_chop_batch_recovery.py` at 1,153 lines, over the 1,000-line limit. These failures are in chop-recovery scope; fix the type mismatch and split that test file, then rerun the respective gates. Closed task sase-1t5 covers different oversized test files and is not a duplicate.

[2026-11-19T00:54:53Z · sase-1t3.13.1.land] DISCOVERED ISSUE: Required check ToolRun 5e0a93f77c4e2b8dc8d6c2d347b0980f failed and unchanged rerun ToolRun fa3de9e517308a662305410923ea6724 reproduced tests/axe/test_axe_chop_batch_recovery.py::test_older_generation_does_not_cancel_a_batch_without_recorded_generation on primary HEAD 571f8c61ce2d849726b755dfec447ecdd5f6984b with sase-core b1a0363997eb8150f8db8a425b83564faf5101f3. The test creates run-new-clan with created_at 2026-11-18T12:00:00Z and no recorded generation, then cancellation for the older generation 20261117_120000 still returns that batch; assertion at line 181 fails. This is in the generation-cancellation contract owned by this epic, outside the unrelated ACE latency paths changed by the current landing. Corroborated on existing task sase-1tm via +1; reconcile the expected no-generation behavior against the current core cancellation contract.

[2026-11-19T10:22:57Z · 1e8--1] CLOSEOUT: All 5 phases (sase-1tc.3.1.1-.5) and child epic sase-1tc.3.1.6 are closed. Closeout blockers from notes #3-#5 resolved: (1) Epic-symbol whitelist: 789e5d0fc5 retired 13 of the 15 rows; 150fce3735 (on origin/master) retired the last two. ChopBatchReplayResult now has a direct named consumer in _chop_batch_recovery_resume_ordinary.py, and ChopBatchReplayError became module-private _ChopBatchReplayError (raised only in chop_batch_replay.py; callers catch the public ChopBatchError family). sase bead epic-symbols sase-1tc.3.1 now reports no entries. (2) Note #4 mypy mismatch in _chop_batch_recovery_observations.py was fixed in 5467217dd0, and the oversized tests/axe/test_axe_chop_batch_recovery.py was split in 6200573ecc. (3) Note #5 generation-cancellation failure: 5467217dd0 moved the sase-core pin, and at that pin Rust chop_batch_generation_matches returns False for the older-generation/no-recorded-generation case. test_older_generation_does_not_cancel_a_batch_without_recorded_generation passes. Verification: 50 targeted chop-batch tests passed, including the subprocess recovery acceptance scenarios, and full sase tool run check f901dd4e9b90438ba51eab179fd85144 passed (all lint stages incl. mypy and symvision, plus scoped tests). Open task sase-1tm's latest note (core pin lacks the generation check) is obsolete for the same reason as (3). Phase sase-1tc.3 and epic sase-1tc are left to their own agents.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.land.md) | [sase-1tc.3.1](sase-1tc.3.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.1][1] | parent epic context | 1 |
| read-by | [agent:sase-1tc.3.1.6.2][2] | Need the parent epic decisions and landing context | 1 |
| read-by | [agent:toobig-a6.test_projected_detail_retention.0][3] | Assess whether the oversized chop recovery tests belong to this active epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-a6.test_projected_detail_retention.0/README.md

<!-- sase:referenced-by:end -->
