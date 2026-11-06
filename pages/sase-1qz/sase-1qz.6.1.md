# Bead: sase-1qz.6.1 — Complete keep-work recovery for hijacked agents

[Bead Pages](../README.md) / [sase-1qz.6](sase-1qz.6.md) / sase-1qz.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.sase-1qz.6` · **Assignee:** `sase-1qz.6.1.land`
**Created:** 2026-11-03 08:05:24 EST · **Closed:** 2026-11-06 12:58:15 EST
**Plan:** [202611/hijack\_keep\_work\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_keep_work_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/hijack_keep_work_recovery.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/hijack_keep_work_recovery.md

<!-- sase:links:end -->

## Description

Recover a hijacked agent exactly once in its held workspace while preserving its work and obligations.

## Notes

[2026-11-06T16:27:45Z · sase-1qz.6.1.land] LAND FOLLOW-UP TRIAGE (sase-1qz.6.1.land): +1 sase-1q0 (microbench, from 6.1.1 #2); +1 sase-1mr (startup toast, 6.1.1 #2 + 6.1.3 #4); +1 sase-1oy (sudo reclaimer, 6.1.2 #1); +1 sase-r2 (pipe e2e agent_session_member node, 6.1.1 #2 + 6.1.7 #1; reopened to ready); +1 sase-1kr (test_revert_git_runner_recovers_stale_index_lock is a third caller of the same aged index.lock recovery, 6.1.7 #1); isolation-guard offender tests/ace/tui/test_log_panel_keymap.py:331 monkeypatch.undo() (6.1.5 #2, 6.1.6 #1, 6.1.7 #1) recorded as DISCOVERED ISSUE corroboration on active epic sase-1ra, whose phase sase-1ra.5 introduced it (still reproduces on acc6f78422). DECLINED: 6.1.1 #1 feature-flags lint (sase-1pk concurrent close, transient; later checks green); 6.1.3 #2 test_monitor_followup_forwards_recorded_vcs_ref (passes on HEAD); 6.1.3 #4 TUI import-closure aggravator (speculative; test_app_import_budget 11 passed on HEAD); 6.1.4 #7 marker-path audit (fixed by sase-1qz.6.1.4.1.6, passes on HEAD); sase-1al panel-pilot sightings (6.1.1 #2, 6.1.2 #1, 6.1.3 #4) already +6 and all predate the sase-1ra.6 grammar-prebuild fix 02e93fd261, not seen in 6.1.7's Nov 6 full run.

[2026-11-06T16:27:57Z · sase-1qz.6.1.land] LAND VERIFICATION (sase-1qz.6.1.land): all 7 phases closed; 290 focused recovery tests pass on acc6f78422; epic-symbols empty for sase-1qz.6.1 and sase-1qz.6; core pin 2815992572 contains the hijack reconcile/preview bindings. Integration review of the ~54 non-epic commits since 83cd8deffe found nothing to rewire (fb61982a41 already threads finalizer starters through recovery admission/successor; 4f9c892c58 leaked-claim repair runs after the hijack custody check; stranded_facts consults hijack custody). REMAINING WORK (blocks close): (1) stale cleanup cannot reach a resolving record once the claim moved to the successor pid (custody.matching_active_record compares expected_claim_owner_pid), and a queued recovery dispatched later by the admission dispatcher is never settled because only _recover_dispatch calls confirm_and_settle — the predecessor stays resolving, done.json recovery.state pending, waiters parked; (2) settle path never registers add_pending_repair before the settle CAS, recover entry returns already_resolved without repair_settled_projection, and pending repairs drain only inside a matched resolving record, so a crash between the ledger move and done.json is never repaired; (3) begin_resolution always records launch_identity/admission_request_id, so Rust hijack_recovery_reconcile can never return_to_held for a proven-absent or terminal-cancelled admission — a crash before admission stays resolving forever and retain messages are dropped; plus expired-hijack waits not parked, misleading already_resolving exit code, _return_to_held CAS-loss result, and the plan's crash-matrix/queued/stale-cleanup test gaps. Planning a tale to finish these and close out.

[2026-11-06T17:57:37Z · sase-1qz.6.1.land] Settlement completion verification: sase tool run check passes every gate except pre-existing symvision stale_checkout rows for sase-1rd.4 (parse_run_prune_review, RunPruneReview, RunPruneReviewCounts, RunPruneProjectAggregate, RunPruneSnapshotItem), which fail identically on the clean base (verified via stash + just _lint-symvision). Unrelated to this tale; no new epic symbols.

[2026-11-06T17:58:15Z · sase-1qz.6.1.land] Settlement completion tale: queued/crashed recoveries auto-settle via per-sweep resolving reconciliation with successor-pid-aware custody; settlement registers pending repair before CAS and drains/repairs on every sweep with locked atomic store; proven-absent launches return to held through Rust not_dispatched with single observer definition; expired hijacks stay parked (neither resolved nor failed) with newest-artifact successor lookup; resume reports queued/launched (exit 0) with reconcile detail and real CAS-outcome reporting. Tests: 34 reconcile + crash-matrix/cleanup/repair/CLI/waits, updated resilience kinds, 126-file broad lane, 96-file affected lane, sase-core check pass; sase check green except pre-existing sase-1rd.4 symvision stale rows (fail identically on clean base).

## Dependencies

- **Blocks:** [sase-1ra.11.1.1](../sase-1ra/sase-1ra.11.1.1.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.land.md) | [sase-1qz.6.1](sase-1qz.6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd02e31`](https://github.com/sase-org/sase-core/commit/cd02e319227a0359d418f4aae60ce93b5e45bb5c) | feat(agent-hijack): return proven-undispatched recoveries to held | [sase-1qz.6.1](sase-1qz.6.1.md) | 2026-11-06 13:00:11 EST |
| sase | [`71011e1`](https://github.com/sase-org/sase/commit/71011e1e10771c589e2c6dd8219dd6a3d32a1040) | feat(hijack-recovery): finish keep-work settlement without user action | [sase-1qz.6.1](sase-1qz.6.1.md) | 2026-11-06 13:50:06 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.cdx][1] | Check dependencies, active epic coverage, and alternatives to the leading task candidates | 1 |
| read-by | [agent:research.3a.cld][2] | Check scope of nested hijack epic running on athena to avoid task conflicts | 1 |
| read-by | [agent:research.3a.final][3] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.6.1.1][4] | Need parent epic DECISIONS and phase breakdown | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.1/README.md

<!-- sase:referenced-by:end -->
