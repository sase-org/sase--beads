# Bead: sase-ns.6.6.6 — Task backlog top five - clear the two red verification gates and the three reproducible test hazards behind them

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.land`
**Created:** 2026-08-17 05:54:38 EDT · **Closed:** 2026-08-17 14:16:30 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

The reproducible-flake gate has no non-epic-owned node holding it red, the serial ACE PNG visual lane is green on master, the last known fork-after-threads hazard in the test suite is gone, and an agent typing a bare `sase` can no longer be silently answered by a different checkout's build. Task beads sase-mv, sase-ny, sase-lk, sase-o5, and sase-o6 are closed on evidence.

## Notes

[2026-08-17T13:29:58Z · 04l--2] DISCOVERED ISSUE: just selection-health --fail-on-new-flake is still red after just test-cost 31946 passed / 10 skipped (monitor 9mp1g9hehqgv) while verifying monitor_node_under_starter. The gate names 3 nodes exceeding tests/reproducible_flake_baseline.txt (records after 2026-08-15T17:22:27Z): tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error (ready sase-ob, +1), tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config (in-progress sase-mv, +1), and tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo (new ready task sase-oh). None are caused by the Agents-tab nesting change. This epic's flake-baseline exit criterion still has these three live holdouts.

[2026-08-17T18:16:30Z · sase-ns.6.6.6.land] LANDED. Verified all five phases against source and commits rather than trusting close notes, integrated post-start changes, and triaged every follow-up.

PHASE VERIFICATION -- ONE PHASE WAS FALSELY CLOSED. sase-ns.6.6.6.4 (forksafe) claimed 'verified no multiprocessing fork remains in that file', but none of that work was ever on master: tests/test_sdd_git_contention.py still carried 'import multiprocessing' plus all four get_context('fork') sites at the exact lines the plan named (322, 346, 420, 492). All 20 sase_<N> workspaces on this host showed 4 fork sites, so it was not merely unstitched -- it existed nowhere. No commit references that bead, while the other four phases each have one. A CORRECTION note is recorded on that phase bead. The land agent implemented it for real: _ForeignEpicLaunchLockWorker runs the target in a daemon thread inside a fresh contextvars.Context, which is a faithful foreign holder because flock ownership belongs to the open file description (so a same-process reopen is refused) and the re-entrancy guard _held_epic_plan_launch_anchors is a ContextVar (so a fresh Context does not short-circuit the real flock wait). Details and the deliberate divergence from sase-o5's prescribed contextmanager seam are in sase-o5's close note.

The other four phases are genuine, confirmed by reading the source: .1 configcache (5e58fb1c8) atomic single-slot publication plus generation guard in config/core.py; .2 goldens (24481abd4) exactly 11 rebaselined PNGs plus the harness fix; .3 supervise (44df0bfb4) _NO_HANG_TIMEOUT = 15.0, _run_supervisor_subprocess, and the '# sase-lk' baseline entry removed; .5 saseinstall (7f3710e3f) staleness.py genuinely wired at init_memory_handler.py:337, not dead code.

INTEGRATION. The load-bearing check: roughly 20 ACE UI commits (relations rail, grouping-cycle o/O, gear iconography, family monitor nesting, unread markers) landed after the 06:25 golden rebaseline, which could have re-staled phase .2's work. A serial visual re-run on current master gives 23 passed -- none re-staled. Phase .1's extracted _config_cache_helpers.py integrates cleanly with c715bacbc's test-file split, no orphans. The reproducible-flake gate now names one node (sase-oh), down from the three recorded in this epic's own DISCOVERED ISSUE note.

EXIT CRITERIA. Task beads sase-mv, sase-ny, sase-lk, sase-o5, sase-o6 are all closed on evidence; sase-o5 was the last and closed in this pass. Of the three flake-gate holdouts, sase-mv is now closed, sase-ob and sase-oh remain ready task beads owned outside this epic.

FOLLOW-UP TRIAGE, all four PROPOSED FOLLOW-UP entries resolved: .1's residual ambient-config-reader finding routed as a DISCOVERED ISSUE to in-progress epic sase-j7 (executor-sharing root, not this epic's mechanism); .2's artifacts_split empty-details goldens filed as sase-os; .4's remaining fork sites filed as sase-or, after the land agent independently re-verified the claim rather than trusting this phase's reporting; .4's model-panel flake corroborated onto existing sase-oh. Nothing was declined.

VERIFICATION RUN. 19 passed in the changed file (blocking site measures 0.16s, proving real flock contention); 41 passed across that file plus tests/test_plan_approval_actions.py with -W error::DeprecationWarning, so no fork warning fires; scoped lane 485 passed; fmt, keep-sorted, ruff, mypy, feature-flags, pyscripts, test-waits, changelog, patch-stitch, toobig, SASE validation and committed-plans all green. NOT VERIFIED: sase-o5's requested '-n 2 --dist=loadfile' xdist lane never ran -- the SASE pytest worker-token broker was fully subscribed by other agents (one holder had held 14 tokens ~2.8h), so it was starved out; the static no-fork-call-sites proof plus the escalated-warning run cover the same property.

KNOWN RED, NOT THIS EPIC: just check fails _lint-symvision on 5 stale --epic-symbol entries keyed to closed phase sase-op.3 (Justfile 336-340). Not caused here -- this epic's diff touches zero files under src/, symvision's only scan root. Routed as a DISCOVERED ISSUE to active epic sase-op, whose in-progress phase sase-op.4 is the plausible re-key target and whose close is already guarded by sase bead epic-symbols. This epic itself has no --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.6.land/README.md) | [sase-ns.6.6.6](sase-ns.6.6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c11e1ad`](https://github.com/sase-org/sase/commit/c11e1ad882196adb00e80513e755b300a6a824cf) | test(sdd): replace forked epic-plan-launch lock holders with an in-process seam | [sase-ns.6.6.6](sase-ns.6.6.6.md) | 2026-08-17 14:20:14 EDT |
