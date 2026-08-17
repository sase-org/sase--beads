# Bead: sase-ns.6 — Work the top five SASE task beads

[Bead Pages](../README.md) / [sase-ns](README.md) / sase-ns.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.land.md) · **Assignee:** `sase-ns.6.land`
**Created:** 2026-08-16 21:02:34 EDT · **Closed:** 2026-08-16 22:16:36 EDT
**Plan:** [202608/task\_backlog\_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)

## Description

The five highest-impact task beads in the sase backlog are fixed and closed: the reproducible-flake gate stops being a permanent red on check-full, the config-center atomic-save node stops flaking under the full parallel lane, `sase bead work` can no longer strand an epic with no agents after a partial cleanup, chezmoi's `just check` is idempotent, and the Artifacts Files PNG snapshot stops erroring during setup.

## Notes

[2026-08-17T01:23:41Z · toobig-2w.split_file.tests.ace.tui.test_agent_completion.0] DISCOVERED ISSUE: Independent 2026-08-16 reproduction of sase-md during a 13-worker full just check: test_save_atomically_replaces_existing_state failed under the full lane and passed immediately in isolation. The triggering diff only splits tests/ace/tui/test_agent_completion.py, so it cannot affect Config Center persistence; evidence was also added to sase-md.

[2026-08-17T02:16:36Z · sase-ns.6.land] VERIFIED all five phases in the source and commits, INTEGRATED the epic with what landed alongside it, FINISHED the bookkeeping three phases skipped, and ROUTED every PROPOSED FOLLOW-UP.

WHAT I VERIFIED IN THE CODE, NOT JUST THE NOTES
- sase-ns.6.1 / task sase-nv (6000a54a1): tools/selection_health parses '# fixed-at: <UTC ts> <node id>' into FlakeBaseline.retirements and builds a RetiredEvidenceOracle threaded through _flake_evidence_nodeids, reproducible_flake_nodeids and stale_flake_nodeids in tests/_test_selection_health_correlation.py. Retirement is applied where evidence is admitted, not inside _has_interleaved_independent_pass, so it discounts a node's own pre-fix failures without inventing passes. Direction 1 (per-node fixed-at) was chosen over the maintenance-free direction 2, keeping a human in the loop about what was declared fixed -- no gate weakening, so no TASK NEEDS APPROVAL was owed. Guardrails are covered by real regression tests, not inspection: test_a_node_still_failing_past_the_fix_point_stays_flagged, test_retiring_one_node_leaves_another_flaky_node_reported, test_omitting_retired_evidence_reproduces_the_unretired_result, plus CLI-level tests for malformed/duplicate directives (exit 2) and for a record with no recorded_at (fails closed, keeps its evidence). RAN IT: the nine 3a22ff04f config/config-cache nodes are retired and gone from the report; the four pre-existing nodes are still reported, as the plan required.
- sase-ns.6.2 / task sase-md (d9b2984a7): root cause is real and correctly described. The tests patched config_center_state.os.replace -- the shared os module -- replacing os.replace process-wide on the xdist worker, which is why unrelated agents reproduced it. save_admin_center_tab_history now calls a module-local _replace_state_file wrapper and the tests patch only that seam. The atomic-replace assertion is intact (the stub still checks the temp file holds new content while the destination still holds old content) and the success test now asserts 'os.replace is real_replace' so the regression cannot come back silently.
- sase-ns.6.3 / task sase-mt (4d8d24eef): prepare_selected_bead_work_force_reuse now verifies every destructive target in a first loop and wipes in a second, so the reported TOCTOU-mid-loop strand is structurally impossible. A genuine mid-wipe failure re-raises naming the already-wiped owners and stating the epic has no live agent for them until rerun. tests/test_bead/test_cli_work_cleanup_apply.py covers all three shapes.
- sase-ns.6.4 / task sase-m8 (chezmoi 61d32ee4): CROSS-REPO, verified in the chezmoi linked repo opened through /sase_repo. '.pytest_cache/' is in .prettierignore. Both prettier recipes (fmt-md line 63, fmt-md-check line 81) run bare prettier with no --ignore-path, so both honor it and stay consistent. REPRODUCED THE ORIGINAL BUG: planted a deliberately unformatted .pytest_cache/README.md and ran 'just fmt-md-check' -> 'All matched files use Prettier code style!'. Probe removed, chezmoi tree clean.
- sase-ns.6.5 / task sase-my (0c8646263): the dead files_options.local_now monkeypatch is gone and no owning call remains (Files groups by_source now), the token asserts moved from Today/Yesterday to Captured/Created, and only artifacts_files_populated_120x40.png was regenerated -- not a broad test-visual-update, which closed bead sase-lo warns rewrites every golden.

INTEGRATION WORK I DID (this is what the epic was missing)
Phase .2 landed 3 minutes before phase .1. It removed the config-center node's baseline entry, but the '# fixed-at:' syntax did not exist yet, so its 21 historical failure records still tripped the gate -- the epic had declared a node fixed and simultaneously made the gate red on it. Closed that in 5feaabc71 by declaring '# fixed-at: 2026-08-17T01:44:57Z' against d9b2984a7. Verified live: 12 in-window failures retired, the node is out of the report (8 exceeding nodes -> 7), the four pre-existing nodes and the three new ones are still reported. Reviewed all 12 non-epic commits since base f8b4ebb11 (bead CRUD split, proc actions split, feature-flag registration/memory, PNG rebaselines, test splits) -- no other conflict or duplication with this epic's surface.

BOOKKEEPING THE PHASES SKIPPED
The plan's 'Bead Bookkeeping -- Every Phase' section required each phase to close its own task bead. Only sase-nv and sase-my were closed. I verified and closed sase-md, sase-mt and sase-m8 myself with root-cause notes, so the epic's stated goal ('the five ... are fixed and closed') is now actually true.

FOLLOW-UPS ROUTED (all four PROPOSED FOLLOW-UP notes, from sase-ns.6.1)
- 'sase init memory --check' drift: already reopened on task sase-n0 by a +1 from sase-ns.6.2. It now exits 0 at HEAD 6000a54a1 on a clean tree; recorded that as an observation on sase-n0 rather than closing it, because one green run of one entry point does not prove the two entry points agree in general.
- test_run_supervisor_idle_timeout_fires_after_output_stalls: exact duplicate of ready task sase-nd; +1'd with this landing's gate evidence. No new bead.
- test_headless_epic_approval_submits_while_inflight_launch_holds_anchor: no owner existed -> filed sase-nz (large, ready) with 12 failure records spanning 2026-08-06..2026-08-17 across six workspaces, plus RELATED notes for sase-ct, sase-j7 and sase-nd. Confirmed it passes in isolation.
- test_usage_limit_failure_disables_only_fakey_and_preserves_error: NOT filed as a task. All 6 failure records post-date eba0eab73, which created tests/fakey/test_usage_limit_e2e.py in phase sase-n4.5.2, and epic sase-n4 is still in progress -- credible causal link, so recorded as a DISCOVERED ISSUE on sase-n4.

ALSO FILED: sase-o0 (medium, ready) -- apply the new fixed-at directive to nodes already fixed before the syntax existed. Measured the proven case: test_override_pills_keep_narrow_top_bar_in_bounds was fixed by 981106799 (task sase-mp, closed as done), its last two failure records are from HEAD 6f7052fc9 which is NOT an ancestor of the fix, and a probe baseline confirms declaring it drops the gate from 7 to 6. Filed rather than done here because this epic's plan explicitly scoped those four nodes out ('must keep being reported') on the stale belief that sase-mp was still live.

HONEST STATE OF THE EPIC'S GOAL: 'just selection-health --fail-on-new-flake' still exits 1, on 7 nodes. The epic removed the permanent, un-clearable red from historical evidence of fixed nodes -- which is what sase-nv actually asked for -- but three of the remaining seven are live flakes with 2026-08-17 evidence that no retirement mechanism can or should hide (sase-nd, sase-nz, and the sase-n4 note), and four were explicitly out of scope. The goal sentence 'the reproducible-flake gate stops being a permanent red' overshoots what the plan scoped; sase-o0 is the honest path to closing the rest.

VERIFICATION: 'just check' exits 0 at HEAD 5feaabc71 -- every lint gate (including symvision), SASE validation, committed plans, and the scoped test lane. Focused re-runs: tests/ace/tui/test_config_center_state.py + tests/test_bead/test_cli_work_cleanup_apply.py -> 26 passed; the four still-reported pre-existing nodes plus the sase-nz node -> 5 passed in isolation. 'just check-full' was not run: it routinely outruns a turn and must go through /sase_monitor, and its only gate beyond 'just check' that this diff could affect is the flake gate, which I ran directly and report above.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) | [sase-ns.6](sase-ns.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5feaabc`](https://github.com/sase-org/sase/commit/5feaabc7122423aff552188be0e662cf2d538684) | fix(selection-health): retire the fixed config-center node's evidence | [sase-ns.6](sase-ns.6.md) | 2026-08-16 22:11:36 EDT |
