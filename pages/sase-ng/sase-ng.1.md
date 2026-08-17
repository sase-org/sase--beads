# Bead: sase-ng.1 — Retire dead ACE in-process launch and cleanup bodies

[Bead Pages](../README.md) / [sase-ng](README.md) / sase-ng.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.land`
**Created:** 2026-08-17 15:16:50 EDT · **Closed:** 2026-08-17 19:51:03 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

ACE's launch and cleanup procs have exactly one implementation each — the durable argv path production actually runs — with no orphaned in-process body family, no vestigial `proc_callable` parameters, no test double that reaches a code path production cannot reach, and no user-facing capability silently dropped on the way.

## Notes

[2026-08-17T22:04:47Z · 057] DISCOVERED ISSUE: just lint now fails the _lint-symvision gate on a clean master checkout (verified via git stash) because the Justfile's _lint-symvision recipe still passes 6 stale --epic-symbol "sase-ng.1.5(...)" entries (record_launched_vcs_xprompt_usage, record_prompt_file_references, record_resolved_vcs_xprompt_usage, save_replayable_vcs_selection, strip_all_vcs_refs, strip_known_project_vcs_refs) for phase bead sase-ng.1.5, which closed. Symvision error: "bead 'sase-ng.1.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol." Discovered while implementing an unrelated plan (artifacts_relations_rail) whose just lint run went red on this pre-existing master issue. Per the sase-o7 pattern (7 prior instances of this exact recurring failure), the land/final-sweep phase (sase-ng.1.6) is the right place to remove these stale entries and clean up any now-unused symbols they exempted.

[2026-08-17T23:00:42Z · sase-ng.1.land] LANDING VERIFICATION (sase-ng.1.land, HEAD c89e5bbeb):

STEP 1 — VERIFY. Reviewed all 6 child beads and every note. Source state confirms the reported work:
- Deleted and confirmed absent: _launch_body.py, _launch_body_impl.py, _launch_body_single.py, _launch_bulk.py, _launch_multi_prompt.py, _launch_multi_model.py, _launch_repeat.py, _launch_background.py, _launch_history.py, _workflow_exec.py, src/sase/axe/run_workflow_runner.py.
- _ref_resolution.py is reduced to module-level resolve_ref_from_prompt() only (RefResolutionMixin._resolve_vcs_from_prompt, strip_all_vcs_refs, strip_known_project_vcs_refs gone), as planned.
- Zero 'proc_callable' references remain anywhere in src/. Only 6 test files still name it and all belong to the deliberately-preserved _submit_session_worker seam (whose parameter is now 'body' in _proc_action_submission.py:197-200).
- Restored capabilities are wired end to end: agent_durable.py:119 sets allow_force_reuse in the RUN_LAUNCH payload -> _launch.py:25 reads it -> plan_force_reuse_launch/apply_force_reuse_launch (src/sase/agent/force_reuse_launch.py) -> rewritten prompt + segment_extra_env. Warning toasts flow _launch.py:159 result_payload['warning_messages'] -> _launch_procs.py:249 _warning_messages_from_payload -> LaunchProcOutcome.warning_messages -> toast at _launch_procs.py:134. Cleanup failure recovery is preserved via _CLEANUP_ERROR_RECOVERY + _apply_cleanup_payload_for_result (ops/commands/agent.py:299-323).

PROPOSED FOLLOW-UPs collected from children and resolved:
- sase-ng.1.2 / sase-ng.1.3 (same defect): the two test_force_reuse_launch_seam.py unauthorized-path assertions over-specifying segment_extra_env. RESOLVED on this tree — _launch.py:114-117 only passes segment_extra_env when a force-reuse plan produced envs, and the whole file is green (12 passed).
- sase-ng.1.1: stale --epic-symbol sase-oc.8(set_completion_summary) re-keyed to sase-oc. RESOLVED — sase-oc closed 20:25Z, the Justfile entry is gone entirely, and set_completion_summary now has 4 production callers (parser_init/parser_repo/parser_var/parser_commands). No task needed.
- sase-ng.1.5: just check-full test-cost budget gate failure. Pre-existing master-wide infra flake already tracked on sase-j0 with a +1 recorded. No new task.
- sase-ng.1.6 x2: filed as task beads sase-p6 (marked-Patch bulk launch is 1 agent not N, size large) and sase-p7 (Ctrl+Space replay target not refreshed from the submitted prompt, size medium), both ready and cross-linked. Both are pre-existing regressions from 0835b38d2 that this epic's plan deliberately scoped out, not defects this epic introduced.
- The epic's own DISCOVERED ISSUE note (stale sase-ng.1.5 --epic-symbol entries failing just lint) is STALE: 0f7d86a66 added those 6 entries and 65b72d43a removed all 6. The Justfile whitelist now holds only sase-n4.5/sase-n4/sase-p1.2 entries; 'sase bead epic-symbols sase-ng.1' reports none.

STEP 2 — INTEGRATE. Nine non-epic commits landed since the epic's first commit 97f5b6f03 (5d98153a7, 6ac274be5, 0496d8bdf, 384063deb, 23180476f, d5ac42693, 5411f5d4a, 24f0c9539, c89e5bbeb). File-level overlap with the epic's 62 touched files is exactly one file, the Justfile, and only in the non-overlapping --epic-symbol block (epic added/removed its own 6 lines; the others touched sase-op and sase-p1.2 lines). Checked the plausible interaction surfaces specifically: the proc_observer split (6ac274be5/0496d8bdf) does not reference any deleted launch/cleanup symbol; the mid-epic docs refresh (5411f5d4a, landed between 0f7d86a66 and 65b72d43a) documents ',<space>' as 'Run agent from current PR' and makes no marked-Patch fan-out claim, and docs/xprompt.md documents '#!name' only through 'sase run', which is the surviving durable route — so no doc contradicts post-epic behavior and no doc edit is owed. Nothing on the tree should now be using what this epic added but is not.

VERIFICATION RUN SO FAR: just install; just lint green end to end (fmt, ruff, mypy, flags, pyscripts, changelog, terminology, toobig) with symvision reporting 'All public/private classes/functions are used properly!'; 83 targeted launch/cleanup tests green across test_force_reuse_launch_seam, test_agent_launch_non_blocking, test_agent_cleanup_procs, test_agent_group_revival_e2e, test_agent_dismiss_persistence, test_agent_marking_save, test_launch_failure_logging, test_prompt_bar_stack_submit_handlers, test_prompt_input_collection_launch, test_resolve_ref_from_prompt. Handing just check-full to a monitor for the combined-tree gate the plan requires before the close.

[2026-08-17T23:51:03Z · sase-ng.1.land--1] LANDING COMPLETE (sase-ng.1.land--1, master c89e5bbeb).

STEP 1 - VERIFY (full detail in the prior LANDING VERIFICATION note on this bead). All 6 phase beads and every note reviewed against the source and the epic's 5 commits (97f5b6f03, f43358dcb, 13e9ccbc9, 0f7d86a66, 65b72d43a) plus dc4ca2057. Deleted-module inventory confirmed absent (_launch_body*.py, _launch_bulk/_multi_prompt/_multi_model/_repeat/_background/_history.py, _workflow_exec.py, axe/run_workflow_runner.py); _ref_resolution.py reduced to module-level resolve_ref_from_prompt(); zero proc_callable references in src/, with only the deliberately preserved _submit_session_worker seam still named in tests. Restored capabilities confirmed wired end to end: allow_force_reuse in the RUN_LAUNCH payload -> _launch.py -> plan/apply_force_reuse_launch; warning toasts payload -> _warning_messages_from_payload -> LaunchProcOutcome toast; cleanup failure recovery via _CLEANUP_ERROR_RECOVERY + _apply_cleanup_payload_for_result. Every child PROPOSED FOLLOW-UP resolved: the two force-reuse seam assertions fixed on this tree by 13e9ccbc9; the stale sase-oc.8(set_completion_summary) entry gone with the symbol now carrying 4 production callers; the test-cost budget miss confirmed as sase-j0's pre-existing master red; sase-p6 (marked-Patch bulk launch fans out 1 agent, large) and sase-p7 (Ctrl+Space replay target not refreshed, medium) filed ready and cross-linked, both pre-existing 0835b38d2 regressions this plan deliberately scoped out. This epic's own DISCOVERED ISSUE note is stale: 0f7d86a66 added the six sase-ng.1.5 --epic-symbol entries and 65b72d43a removed all six; sase bead epic-symbols sase-ng.1 reports none, and the Justfile whitelist holds only sase-n4.5/sase-n4/sase-p1.2 lines.

STEP 2 - INTEGRATE. Nine non-epic commits landed since 97f5b6f03 (5d98153a7, 6ac274be5, 0496d8bdf, 384063deb, 23180476f, d5ac42693, 5411f5d4a, 24f0c9539, c89e5bbeb). File-level overlap with the epic's 62 touched files is exactly one file, the Justfile, in a disjoint --epic-symbol block. The proc_observer split references no deleted launch/cleanup symbol; the mid-epic docs refresh documents ',<space>' as 'Run agent from current PR' and '#!name' only through 'sase run' (the surviving durable route), so no doc contradicts post-epic behavior and no doc or code edit is owed.

VERIFICATION - just check-full at c89e5bbeb (monitor 7jzhrte86141, 23m3s): every fmt/keep-sorted/ruff/mypy/flags/pyscripts/test-waits/changelog/terminology/symvision/toobig gate green, SASE validation and committed-plans green, and the full cost lane green at 32563 passed / 13 skipped / 0 failed in 1123.90s. The run failed only in tools/check_test_cost_budgets, the standing master-red gate tracked on sase-j0; numbers recorded there as a note (this reporter already counted via sase-ng.1.5/1.6). It missed 9 keys where the two earlier runs on the same tree family missed the usual 4; re-checking all three recordings against the committed budgets isolates the extra 5 to host load (12 workers / 1076s vs 14 workers / 672-754s), all wall-derived plus per-worker collection CPU, so nothing tree-attributable.

Because test-cost aborts check-full before its last gate, I ran the trailing gate separately: just selection-health --fail-on-new-flake named 3 nodes, 2 of them this epic's own pre-fix evidence - tests/test_force_reuse_launch_seam.py::test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse and ::test_sidecar_without_authorization_still_rejects_forced_reuse, which failed on trees 88a8400 (dirty), 97f5b6f03 (x2) and 6ac274be5 while the helper asserted launch_agents_from_cwd(prompt, segment_extra_env=None), until 13e9ccbc9 dropped the over-specified keyword. Retired that evidence through the baseline's documented mechanism: a '# fixed-at: 2026-08-17T20:21:41Z' block in tests/reproducible_flake_baseline.txt naming sase-ng.1.1 and 13e9ccbc9 (6 records retired; the 20:37Z record on the pre-fix 6ac274be5 tree stays live by the file's documented known limitation, one record being below the two-failure evidence bar). The gate now names only tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo, which is sase-oh's pre-existing holdout - +1 recorded there with this reproduction; that node is untouched by this epic. Re-verified after the edit: the 12 force-reuse seam tests

… and 1879 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.1.land.md) | [sase-ng.1](sase-ng.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f77d940`](https://github.com/sase-org/sase/commit/f77d940d6ca0767966c6b377f8924f72c1d13e68) | test(flake-baseline): retire pre-fix force-reuse seam evidence | [sase-ng.1](sase-ng.1.md) | 2026-08-17 19:56:11 EDT |
