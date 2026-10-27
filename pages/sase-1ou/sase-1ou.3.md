# Bead: sase-1ou.3 — Make the weight-two land-agent-session capacity e2e load-robust (sase-12f)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.3` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT · **Closed:** 2026-10-27 13:20:36 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

capacity-e2e: find what consumes the fakey land agent's 5 s budget under load in tests/fakey/test_monitor_capacity_e2e.py (delayed child bootstrap, capacity scan under the host-wide slot lock, or harness polling), fix the cause instead of the timeout, prove it with a loaded stress loop, and close sase-12f.

## Notes

[2026-10-27T14:41:51Z · sase-1ou.3] PLANNING EVIDENCE: At clean base e608de2db6 the unchanged target passed once in 65.58s, with 61.89s test-call time and 60.608s in settle_named_proc before successor startup. The shared fakey harness creates flat ace-run timestamp paths, while production starter settlement uses canonical date-sharded paths. An in-memory diagnostic probe using canonical agent paths preserved all assertions and five-second budgets and passed in 4.32s total / 1.85s call; the real starter-settlement wait saw done.json already present and returned True immediately. No source implementation edits were made. This proves the wasted settlement wait, not the historical load-only exit-124 cause. The validated medium tale sase_plan_capacity_e2e_load_robust.md requires comparable isolated and loaded before/after evidence before closure. epic-symbols reported no entries for this phase.

[2026-10-27T17:20:26Z · sase-1ou.3--2] FINAL EVIDENCE 2026-10-27: cause is flat ace-run timestamp dirs in tests/fakey/_runner_slot_harness.py invisible to production canonical date-sharded starter settlement, forcing 60s settle timeout; fix uses canonical_agent_artifact_path plus settlement-observation assertions, 5s budgets intact, no exit 124. Stress on fixed tree: 10x isolated target node 10/10 passed 4.6-5.6s total each call 2.0-2.6s loadavg 25-29; 20x full tests/fakey/test_monitor_capacity_e2e.py at -n4 20/20 passed 6 passed each 9-12s loadavg 26-36; harness consumers 18 passed 1 skipped plus zero-weight 1 passed; selection_health retires target 7 pre-fix records via fixed-at 2026-10-27T16:09:47Z with 41 unrelated live flakes remaining. Final check tool run 44191d994937219f194507bf31233112 exit 1 with only 3 KNOWN no NEW: test_checked_in_snapshot_has_no_drift + test_current_structural_view_matches_checked_in_snapshot (witness 0832dea1c87b939b0133374d264d28ba, pre-existing sase-1om snapshot drift) and test_tui_app_import_stays_under_startup_budget (witness 01564beb93f5085605d33a22bce43f1f, pre-existing unrelated).

[2026-10-27T17:20:36Z · sase-1ou.3--2] Phase done: capacity-e2e root cause fixed (canonical artifact path, no 60s waste), stress 10/10 isolated + 20/20 full-file green with 5s budgets, final check 44191d99 exit 1 with only 3 pre-existing KNOWN, epic-symbols empty. sase-1ou, ancestors, sase-12f left open.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.3.md) | [sase-1ou.3](sase-1ou.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a42eedc`](https://github.com/sase-org/sase/commit/a42eedc1c4679612ccfbcc277f302c88c1960b2f) | fix(tests): make monitor capacity e2e load-robust via canonical artifact path | [sase-1ou.3](sase-1ou.3.md) | 2026-10-27 13:22:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.3--2][1] | Verify phase state before recording stress evidence and closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.3.md

<!-- sase:referenced-by:end -->
