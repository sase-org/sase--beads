# Bead: sase-ns.6.6 — Task backlog top five — turn the mandatory verification gates green

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.land`
**Created:** 2026-08-17 04:03:10 EDT · **Closed:** 2026-08-17 05:35:19 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

`just check-full`'s last gate (`just selection-health --fail-on-new-flake`) stops reporting nodes that were already fixed, and stops reporting the two live full-parallel-lane flakes it currently names; the recurring generated-memory drift that flips `just check` red at the SASE validation step can no longer reappear undetected; and monitor reconciliation's locked settle path stops issuing an archive-scaled artifact-index query per candidate. Closes task beads sase-o0, sase-nd, sase-nz, sase-n0, and sase-ne.

## Notes

[2026-08-17T09:35:19Z · sase-ns.6.6.land] VERIFIED (step 1). All five phases closed with work confirmed in source, not just in notes. sase-ns.6.6.1/72d3d5c9f: four # fixed-at: retirements in tests/reproducible_flake_baseline.txt, each tied to a named fix commit (981106799, 5d0bcf9e8, 57c71d17a, 278cc810b); no file-wide # effective-after: bump and no plain suppression, so the header's 'debt to remove, not suppressions to grow' guardrail held. sase-ns.6.6.2/99b4e43a1: re-verified the structural claim myself -- sase validate's memory step shells out to 'sase init memory --check' as a subprocess, so both entry points funnel through one plan_init_memory -> plan_memory_root -> render_expected_memory_files chain and cannot disagree; the regression gate tests/main/test_init_memory_committed_drift.py landed and is hermetic (scratch HOME/CONFIG_DIR, use_chezmoi=False). No memory-content edit was made, so the approval boundary was respected. sase-ns.6.6.3/2f41353b5: read every call site -- reconcile_dead_supervisors (store.py:416), active_monitor_for_lane (234), monitor_blocking_start_for_lane (267) and stop_monitor's three dead-supervisor branches (305/313/321) now inject path-direct read_monitor_marker, whose (project_name, artifacts_dir) -> MonitorRecord | None signature matches the GetMonitor alias, so the locked settle (reconcile.py:78) and locked re-read (123) are bounded with no signature change; bound pinned by a 3-vs-8-candidate one-query test. sase-ns.6.6.4/f9ab15d9c: the no-hang bound was reformulated, not weakened -- subprocess.run(timeout=_NO_HANG_TIMEOUT) still fails a genuine hang, and the idle-timeout assertions gained a live_reply.md check. sase-ns.6.6.5/b6246f1cf: diffed the assertions before and after -- all four patches byte-identical, start_launch.assert_called_once() and the mon-contended assertion intact; the only dropped assertion tested the deleted harness subprocess. Verified the in-process holder writes the same JSON shape production epic_plan_launch_lock writes (cli_work_from_plan_store.py:219-227).

INTEGRATED (step 2). No commits landed between this epic's start (2026-08-17T08:03:10Z) and its landing other than its own five, and origin/master matches HEAD, so there was no external drift to reconcile. Checked the epic against the commits immediately preceding it: phase 3's new test correctly lands in tests/monitor/test_monitor_store_reconcile_queries.py, the file dc221a458 had just split out, and phase 1's retirements follow the # fixed-at: convention 6000a54a1/5feaabc71 established rather than duplicating it.

COMPLETED THE DEFERRED EPIC WORK (cf7eeee03). Both deflake phases could not declare their own # fixed-at: entries because the directive must name an already-existing commit; both left that to the land agent and the plan's Done Means required it. Added # fixed-at: 2026-08-17T08:41:25Z for the monitor node (f9ab15d9c, retires 3 records, newest 2026-08-17T01:20:25Z) and # fixed-at: 2026-08-17T08:54:01Z for the approval node (b6246f1cf, retires 12 records, newest 2026-08-17T01:37:59Z). Confirmed against the durable store that every retired record predates its fix commit and neither node has failed since. just selection-health --fail-on-new-flake went 7 exceeding nodes at triage -> 4 -> 2; just check green.

GATE STATE AT CLOSE. Two nodes still exceed the baseline, both outside this epic: tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error (explicitly out of scope, owned by in-progress epic sase-n4) and tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config (surfaced during the epic, 13 of its 14 records predate the epic, routed to sase-mv).

TASK BEADS. All five closed as done with verification notes: sase-o0, sase-n0, sase-ne, sase-nd, sase-nz. No TASK NEEDS APPROVAL note was left on any of them; a full sase bead search confirms none is outstanding anywhere, so nothing is owed to the project owner from this round.

FOLLOW-UPS ROUTED (step 3). Four PROPOSED FOLLOW-UP notes were collected from the child beads. Two were epic work and are done above (the two # fixed-at: retirements). The rest, all re-verified independently before routing: (1) tests/test_sdd_git_contention.py still forks epic-plan-launch lock holders from multi-threaded xdist workers -- confirmed two helpers and four fork call sites (lines 322/346/420/492) in the current tree; new task sase-o5, size medium, with RELATED notes to sase-nz and sase-j7. (2) The global sase on PATH is a uv tool install pinned to a separate checkout -- confirmed by shebang (/home/bryan/.local/share/uv/tools/sase/bin/python3) and by the global build lacking the 'flag' subcommand this workspace's .venv/bin/sase has; new task sase-o6, size medium, with RELATED notes to sase-n0 and sase-i7. This is the most credible mechanism yet for sase-n0/sase-i7's cross-agent drift disagreements. (3) sase-j7's leak detector does not instrument interpreter thread count at fork time -- recorded as a DISCOVERED ISSUE note on in-progress epic sase-j7 rather than as a task, because the detector is that epic's own deliverable. (4) tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config full-lane failure -- corroborated as a +1 on ready task sase-mv (now +18) rather than filed fresh: same file, same process-global config-cache class, same full-lane-only signature, same remediation. Nothing was declined.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) | [sase-ns.6.6](sase-ns.6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf7eeee`](https://github.com/sase-org/sase/commit/cf7eeee03f6c779e0ac4ba9f202a6cf5b2968dab) | test: retire the deflaked monitor and approval nodes | [sase-ns.6.6](sase-ns.6.6.md) | 2026-08-17 05:25:58 EDT |
