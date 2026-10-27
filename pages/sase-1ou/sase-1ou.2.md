# Bead: sase-1ou.2 — Stop the ToolRun store failing with "database is locked" under parallel load (sase-18t)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.2` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT · **Closed:** 2026-10-27 18:05:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

toolrun-busy: identify which sase-core ToolRun store transactions hold the SQLite write lock while launcher, settle and show paths read it, fix the contention at its source in sase-core with a principled busy policy, move the core pin, retire the tests/tool/ baseline entries with fixed-at, and close sase-18t.

## Notes

[2026-10-27T22:07:09Z · sase-1ou.2.1.land--1] CHILD LANDING VERIFIED: Child epic sase-1ou.2.1 and both phases are complete. The normal child close also completed this delegated parent phase with resolution done and reason "delegated work landed". I independently verified this phase's approved child-plan scope, every child note, source/tests, commits, inherited decisions, and post-start integration drift. Core commits 6d11122e and 3f8baa79 fix the measured store-open/schema/WAL/last-close lock mechanism and share one elapsed contention budget. Primary 57d5f411e4 delegates defaults to Rust, preserves real caller deadlines, and pins 3f8baa79 without regressing prior pin ancestry. No new caller conflicts or integration edits were needed; both checkouts still match remote master. Both epic-symbol audits are empty.

EVIDENCE FOR OUTER LANDER: file:explicit:b0d1fd4be5d7f8c6c632927d and raw file:explicit:c0f4bd59f97240f4bbc90b82 preserve all denominators, original failures, provenance, and clean-base witnesses. Each of ten final nodes passed 10/10 serial, 20/20 loaded and 3/3 controlled; natural before runs also passed, so natural reproduction is not claimed. Controlled 400ms last-close failed old show 10/10 and passed fixed show 10/10. Both watchdog nodes and settlement notification were independently attributed (old 3/3 fail, fixed 3/3 pass), and only their three baseline entries were retired; six remain active. Corrected 25ms explicit budgets measured at most 25.403ms, with no duplicate events/runs or quarantine. Final core and primary guarded checks passed (b2631e20ccc7a88c5b307a70b5c3f5bd and 1c557cb47b1f4832fb4c616a46b209c3). Fresh landing monitor jfvk1yqhx7dv rebuilt the missing local Rust extension and passed all 272 tests across 14 affected files with eight workers, exit 0; source stamp matches current pinned core. See file:monitor-retained-log:jfvk1yqhx7dv and ToolRun 04e34dc29a50a66870ece001797c3478. No check-full was run.

FOLLOW-UP DISPOSITION: Phase 1 note 2 corroborated listener flake sase-1gz. Phase 2 note 2 recorded retained unproven nodes on existing sase-18t; no duplicate task. The sase-19t duplicate-closure proposal was declined because its original exception signature is missing despite 21/21 handoff passes, with this limit recorded on that task. Phase 2 note 3 became ready large flake sase-1p2 for the distinct child-alive assertion (1/20 earlier loaded failures, then unchanged-tree passes); it is linked to 18t/19c with raw evidence and does not establish permanent child survival. Phase 2 note 5 corroborated sase-1ic for the clean-base module-count failure and active owning epic sase-1om for completion drift; no duplicate tasks. Phase 2 note 7's 41 identical preexisting selection-health exceedances were recorded on sase-1ou for existing phase-1/outer-lander reconciliation; duplicate umbrella task declined. None of the three retired ToolRun nodes exceeded baseline.

Per the approved child plan's explicit ownership rule, this phase's completion leaves task sase-18t closure and sase-19t disposition to the outer lander; no unsupported task closure is claimed. Containing epic sase-1ou remains for its own waiting land agent. The inherited dormant_flakes=close decision remains applicable to that outer landing. Full consolidated audit and every proposal outcome are on child epic sase-1ou.2.1.

[2026-10-27T22:07:38Z · sase-1ou.2.1.land--1] CHILD LANDING VERIFIED: Child epic sase-1ou.2.1 and both phases are complete. The normal child close also completed this delegated parent phase with resolution done and reason "delegated work landed". I independently verified this phase's approved child-plan scope, every child note, source/tests, commits, inherited decisions, and post-start integration drift. Core commits 6d11122e and 3f8baa79 fix the measured store-open/schema/WAL/last-close lock mechanism and share one elapsed contention budget. Primary 57d5f411e4 delegates defaults to Rust, preserves real caller deadlines, and pins 3f8baa79 without regressing prior pin ancestry. No new caller conflicts or integration edits were needed; both checkouts still match remote master. Both epic-symbol audits are empty.

EVIDENCE FOR OUTER LANDER: file:explicit:b0d1fd4be5d7f8c6c632927d and raw file:explicit:c0f4bd59f97240f4bbc90b82 preserve all denominators, original failures, provenance, and clean-base witnesses. Each of ten final nodes passed 10/10 serial, 20/20 loaded and 3/3 controlled; natural before runs also passed, so natural reproduction is not claimed. Controlled 400ms last-close failed old show 10/10 and passed fixed show 10/10. Both watchdog nodes and settlement notification were independently attributed (old 3/3 fail, fixed 3/3 pass), and only their three baseline entries were retired; six remain active. Corrected 25ms explicit budgets measured at most 25.403ms, with no duplicate events/runs or quarantine. Final core and primary guarded checks passed (b2631e20ccc7a88c5b307a70b5c3f5bd and 1c557cb47b1f4832fb4c616a46b209c3). Fresh landing monitor jfvk1yqhx7dv rebuilt the missing local Rust extension and passed all 272 tests across 14 affected files with eight workers, exit 0; source stamp matches current pinned core. See file:monitor-retained-log:jfvk1yqhx7dv and ToolRun 04e34dc29a50a66870ece001797c3478. No check-full was run.

FOLLOW-UP DISPOSITION: Phase 1 note 2 corroborated listener flake sase-1gz. Phase 2 note 2 recorded retained unproven nodes on existing sase-18t; no duplicate task. The sase-19t duplicate-closure proposal was declined because its original exception signature is missing despite 21/21 handoff passes, with this limit recorded on that task. Phase 2 note 3 became ready large flake sase-1p2 for the distinct child-alive assertion (1/20 earlier loaded failures, then unchanged-tree passes); it is linked to 18t/19c with raw evidence and does not establish permanent child survival. Phase 2 note 5 corroborated sase-1ic for the clean-base module-count failure and active owning epic sase-1om for completion drift; no duplicate tasks. Phase 2 note 7's 41 identical preexisting selection-health exceedances were recorded on sase-1ou for existing phase-1/outer-lander reconciliation; duplicate umbrella task declined. None of the three retired ToolRun nodes exceeded baseline.

Per the approved child plan's explicit ownership rule, this phase's completion leaves task sase-18t closure and sase-19t disposition to the outer lander; no unsupported task closure is claimed. Containing epic sase-1ou remains for its own waiting land agent. The inherited dormant_flakes=close decision remains applicable to that outer landing. Full consolidated audit and every proposal outcome are on child epic sase-1ou.2.1.

[2026-10-27T22:09:59Z · sase-1ou.2.1.land--1] FINAL CLOSEOUT: Child epic plan:202610/toolrun_sqlite_contention.md is marked status: done. Post-close just symvision exited 1 solely at the first stale exemption sase-1p1.2(other_id) on unchanged primary master 57d5f411e4; recorded on causal active Footprint epic sase-1p1 and corroborated existing task sase-o7 (+23). This phase and its child epic have no epic-symbol entries. The 272 affected-file tests passed after exact-source extension rebuild. Full child audit and follow-up dispositions are on sase-1ou.2.1; outer epic/task closure remains with the outer lander.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md) | [sase-1ou.2](sase-1ou.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.2.1.1][1] | Need outer phase context, DECISIONS, and sase-18t evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.2.1.1/README.md

<!-- sase:referenced-by:end -->
