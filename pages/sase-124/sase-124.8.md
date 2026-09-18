# Bead: sase-124.8 — Finish Agents freshness correctness and acceptance

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-124.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.land.md) · **Assignee:** `sase-124.8.land`
**Created:** 2026-09-17 17:43:29 EDT
**Plan:** [202609/finish\_agents\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agents_freshness.md)

## Description

Cached-roster capacity stays correct across hidden rows, empty rosters, and interleaved loads; attention polling never delays local refreshes or loses a requested network refresh; fresh measurements establish the integrated sase-124 freshness contract.

## Notes

[2026-09-18T02:32:38Z · sase-124.8.land] LANDING AUDIT 2026-09-17 at c320b2b6ca: intentionally leaving this child epic in progress and its linked plan unchanged. Reviewed the epic history, all three closed children and all four child notes, the full accepted plan, source and tests, all three matching commits (f1616c505e, 9a1d5d67a, 76df54778f), the predecessor audit/reproducer artifacts, and every commit after the first child-epic commit. HEAD, origin/master, and their merge base all match c320b2b6ca.

VERIFIED IMPLEMENTATION: current source uses the canonical capacity roster including empty and hidden/local rows; guards capacity results with roster/input generations; retains the prior valid capacity while stale work is recomputed off-thread; detaches cache/network attention work; preserves a stronger network request behind cache work; records completed-only attention mode/duration/outcome/coalescing counters; and keeps the 60-second network cadence. The audited reproducer now reports hidden capacity 2/2, empty-roster scheduling, stale ordering 2/2, no UI-thread stale-boundary call, attention modes [true,false], and Agents refresh before blocked cache release. It emits only its known mocked-coroutine warning. Focused capacity/attention tests passed 84/84.

INTEGRATION: reviewed all post-start commits. Relevant concurrent sase-127 changes are 7058f16ceb bounded-load convergence, 5b7c4553cc no-op fleet projection skipping with forced remote sources, and 677ed7d8e4 stable active-search guard. Their load-tier, fleet, and display suites passed 52/52 with the child changes. Gate commits 1d14218a3c and child commit 76df54778f keep failure data receipt-scoped; sase-zr.7.3/.5 remain in progress, so no top-level marker contract was invented. New screenshot commits can establish a dedicated tmux window but do not substitute for trace/perf evidence. No source integration edit is currently justified.

CONFIRMED REMAINING EPIC WORK: phase sase-124.8.3 did not satisfy its accepted acceptance phase. Its busy capture records refresh.auto_tick p50/p95/max 124/3108/3906 ms and six bench_tui_jk assertion misses, but does not causally attribute those misses. It explicitly leaves the ten-minute idle window, scripted marker latency with/without watcher delivery, capacity-on-entry latency, tick p95 under 1000 ms, no attention-attributable tick over two seconds, no unread/countdown main-thread stall over 500 ms, and zero idle slow full loads unverified. Missing evidence cannot be converted to success or a normal close. No force close or parent mutation was attempted. Current sase bead epic-symbols sase-124.8 reports no entries.

PROPOSAL OUTCOME: sase-124.8.2 note 1 is a genuine independent full-parallel/pass-isolation flake. Used sase_new_task; searched all statuses/types, swept last-week tasks, inspected the retired umbrella and plausible active-epic scope, and recovered the phase chat. No node-specific duplicate exists and evidence does not establish the process-global-state root owned by sase-j7. Retired umbrella sase-ct explicitly requires a narrow node-named task. Created ready large flake task sase-129 for tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked, preserving the 1/1 full-lane failure and 0/2 immediate serial reruns. The required typed related link to sase-ct was attempted but rejected by the dirty hidden plans clone; the relation remains explicit in sase-129 prose, and this independent link-lane recurrence was corroborated on existing ready task sase-10y (+11). This flake is not child-epic work.

HANDOFF: authored remaining-only two-phase plan sase_plan_complete_agents_freshness_acceptance.md with parent_bead=sase-124.8. It covers controlled busy/idle/scripted acceptance and evidence-driven remediation only, preserves concurrent load/fleet/search behavior, excludes parent close/Symvision/plan-status duties, and passed validate --explain plus revalidation with zero warnings. Preparing to submit through sase_plan. The successor land agent must recheck descendants/notes and post-child drift, run combined just check-full through sase_monitor, triage every new proposal, and close normally only after the original target matrix is complete.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.8.land.md) | [sase-124.8](sase-124.8.md) | 0 |
