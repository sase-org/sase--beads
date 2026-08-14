# Bead: sase-lb.1 — One live agent per numbered workspace — close the monitor claim hole

[Bead Pages](../README.md) / [sase-lb](README.md) / sase-lb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.land`
**Created:** 2026-08-14 11:09:07 EDT · **Closed:** 2026-08-14 14:06:25 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

A numbered `<project>_<N>` workspace checkout is never occupied by two live agents at once. Every process that works inside a numbered workspace holds the RUNNING-field claim for that exact number for as long as it is in there, the claim's PID is always a live process, and any code path that cannot satisfy that invariant fails loudly instead of silently running unclaimed.

## Notes

[2026-08-14T17:27:48Z · sase-lz.land--1] DISCOVERED ISSUE: During unrelated sase-lz landing verification on 2026-08-14 at HEAD 6ee334708, monitored 'just check-full' failed in the full test-cost lane with an xdist worker crash while running tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop. The exact node passed when rerun directly together with the other reported failure via 'just test tests/llm_provider/test_commit_finalizer_baseline.py::test_pre_existing_sibling_file_is_excluded_and_reported_separately tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop'. The sase-lz landing commit only touched Models-panel selector-builder docs/code/tests, so this is unrelated to that epic. Routed here because the node is in deferred workspace/workspace-claim runner outcomes and this active epic owns the workspace-claim invariant.

[2026-08-14T18:06:25Z · sase-lb.1.land--1] All seven phases verified against their notes and against source: sase-lb.1.1 (workspace_num recorded in agent_meta.json — src/sase/agent/*, confirmed via 44 targeted tests); sase-lb.1.2 (resolve_workspace_num_for_dir() in src/sase/workspace_provider/lookup.py:35, confirmed present); sase-lb.1.3 (monitor start claims the numbered workspace its command runs in — src/sase/monitor/start.py, workspace_num wiring confirmed present); sase-lb.1.4 (monitor handoff claim-ownership check before the runner's SIGTERM/monitored skip); sase-lb.1.5 (resolve_consistent_workspace_pair() in lookup.py:73, wired into monitor/followup.py and agent/_family_attach_launch.py, confirmed present); sase-lb.1.6 (commit-finalizer dirty-path baseline capture/exclusion, src/sase/llm_provider/commit_finalizer_baseline.py, confirmed present); sase-lb.1.7 (workspace occupancy diagnostics + doctor surfacing + claim-invariant regression).

Mid-epic integration conflict: bead sase-ly's discarded-dirty-work guard (landed mid-epic) rejected phase sase-lb.1.6's test mock, which deleted its own uncommitted file without advancing HEAD — sase-lb.1.7 recorded this as a PROPOSED FOLLOW-UP (test_pre_existing_sibling_file_is_excluded_and_reported_separately failing standalone). This was epic-caused fallout from the sase-ly integration, not an unrelated follow-up, so it was fixed rather than filed as a task: the mock now commits its own file via git, and the test additionally asserts the pre-existing sibling file is neither committed nor discarded.

Baseline-inheritance regression and fix (plan 202608/lane_baseline_inheritance.md): sase-lb.1.6's unconditional per-run baseline capture broke monitor follow-up / family-attach continuations, which re-baseline against a workspace that already contains their own lane's uncommitted work, causing the finalizer to misreport that work as pre-existing dirt no one would ever commit. Fixed by inheriting the family-attach parent's commit_finalizer_baseline.json byte-for-byte instead of capturing fresh (src/sase/axe/run_agent_runner_bootstrap.py::_inherit_parent_commit_finalizer_baseline), falling back to a fresh capture whenever there is no plan, no parent baseline file, or the copy fails. 5 new bootstrap tests + 1 new end-to-end finalizer test added; verified via monitored 'just check-full' (workspace sase_11, 2026-08-14T17:17:54Z-17:54:46Z): every lint gate, SASE validation, committed-plan validation, and the full pytest test-cost lane passed clean (0 failures). The run's only failure was the pre-existing, unrelated 'just selection-health --fail-on-new-flake' gate (15 reproducible-flake node IDs drawn from historical cross-workspace records, none touching this epic's diff) — diagnosed, corroborated onto existing tracked tasks sase-jq and sase-lc, and documented on already-open epic sase-j7 (which owns this flake class); not a regression from this epic, so not a landing blocker.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-lb.1.land.md) | [sase-lb.1](sase-lb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@e2df552`](https://github.com/sase-org/sase--plans/commit/e2df5527ccd3bfc8801d29f28d34e5e777ea3ed0) | docs(plans): mark workspace\_claim\_invariant epic plan done | [sase-lb.1](sase-lb.1.md) | 2026-08-14 14:10:39 EDT |
