# Bead: sase-i8.10.4 — Land the epic and file the remaining follow-ups

[Bead Pages](../README.md) / [sase-i8.10](sase-i8.10.md) / sase-i8.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.land/README.md) · **Assignee:** `sase-i8.10.4` · **Size:** small
**Created:** 2026-08-10 08:27:16 EDT · **Closed:** 2026-08-10 10:30:45 EDT
**Plan:** [202608/merge\_visibility\_dispatch\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_visibility_dispatch_fix.md)

## Description

land: refresh the stale contract manifest, file the surviving follow-up proposals as sized task beads, close the epic with a verification note, run symvision, and mark both plan files done.

## Notes

[2026-08-10T14:23:31Z · sase-i8.10.4] PROPOSED FOLLOW-UP: mypy never checks tools/ — confirmed tools/validate_sase_core_rs has 3 real union-attr errors (lines 561,564,567) invisible to `just check` because [tool.mypy].files in pyproject.toml covers only "src". Widen mypy to tools/ to catch this class of bug. (originally proposed by sase-i8.2)

[2026-08-10T14:24:44Z · sase-i8.10.4] PROPOSED FOLLOW-UP: tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch fails under xdist with "research.0.cdx" already reserved on the second launch, passes alone. Confirmed still present in tree, not re-run to reproduce. (originally proposed by sase-i8.3)

[2026-08-10T14:25:44Z · sase-i8.10.4] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles failed once in a full lane, passed on isolated and xdist reruns. Confirmed still present in tree, not re-run to reproduce. (originally proposed by sase-i8.4)

[2026-08-10T14:26:28Z · sase-i8.10.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_offers_project_local_xprompts_by_canonical_name and ::test_vcs_tag_directory_key_spelling_also_resolves are xdist-order sensitive. Confirmed both still present in tree, not re-run to reproduce. (originally proposed by sase-i8.6)

[2026-08-10T14:27:19Z · sase-i8.10.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_tasks_pane_store.py::test_following_a_live_store_row_bypasses_the_mtime_cache[success-True] reproduces independently with known_mtime None. Confirmed still present in tree, not re-run to reproduce. (originally proposed by sase-i8.7)

[2026-08-10T14:28:12Z · sase-i8.10.4] PROPOSED FOLLOW-UP: vcs_repo_stats (src/sase/vcs_provider/plugins/_git_query_ops.py) counts commits with `git rev-list --count HEAD` and contributors with `git shortlog -sne HEAD` — confirmed both still count merge commits with no --no-merges filter, so both start over-counting once squash-merge is off. Epic sase-i8 plan deliberately deferred this to a follow-up.

[2026-08-10T14:28:53Z · sase-i8.10.4] PROPOSED FOLLOW-UP: src/sase/updates/incoming_commits.py _fetch_git_incoming_commits lists/counts incoming commits with plain `git rev-list --count` and `git log` over a revision range — confirmed no merge-awareness. A second commit-listing surface that will start showing/counting merge commits once squash-merge is off; MergeVisibility is now available to it.

[2026-08-10T14:29:25Z · sase-i8.10.4] PROPOSED FOLLOW-UP: tests/test_run_pytest_main.py::test_main_cost_mode_arms_only_the_cost_recorder fails reproducibly on master (confirmed via isolated pytest run) — HEALTH_PLUGIN_MODULE unexpectedly present in the cost-mode command, asserted absent. Unrelated to this epic (tools/run_pytest cost/health plugin arming logic); flagged by phase accept (sase-i8.10.3) full-suite baseline.

[2026-08-10T14:29:58Z · sase-i8.10.4] CONFIRMED: sase-core-rs 0.21.3 gap (sase-i8.8) resolved by the 0.23.0 floor — pyproject.toml pins sase-core-rs>=0.23.0,<0.24.0 and `just install` built/installed sase-core-rs 0.23.0. CONFIRMED: markdown format gate on sase/memory/build_and_run.md (sase-i8.7, sase-i8.8) resolved — `just fmt-check` passes prettier over all markdown cleanly. CONFIRMED: generated memory README drift (sase-i8.8) no longer reproduces — `sase init memory --check` reports nothing to do; not filed.

[2026-08-10T14:30:45Z · sase-i8.10.4] Refreshed contract manifest: tools/refresh_contract_manifest is a no-op (tests/contract_manifest.txt already includes tests/test_probe_core_floor_tool.py, fixed by an unrelated commit that landed on master since the plan was written); tests/test_contract_manifest.py -q passes (3 passed). Confirmed already-resolved items: sase-core-rs 0.23.0 floor is installed (pyproject.toml pins >=0.23.0,<0.24.0, just install built/installed 0.23.0), just fmt-check passes prettier over all markdown including sase/memory/build_and_run.md, and sase init memory --check now reports nothing to do (memory README drift no longer reproduces, so not filed). Confirmed and recorded 7 still-open follow-ups as PROPOSED FOLLOW-UP notes on this bead for the land agent to triage: mypy never scanning tools/ (3 real errors confirmed in tools/validate_sase_core_rs), four known-flaky/order-sensitive tests carried forward from sase-i8.3/.4/.6/.7 (confirmed still present in tree), vcs_repo_stats and incoming_commits.py both confirmed not merge-aware (plain git rev-list --count / git log, no --no-merges or MergeVisibility use), and a newly-confirmed reproducible failure in tests/test_run_pytest_main.py::test_main_cost_mode_arms_only_the_cost_recorder (unrelated to this epic). No source files changed by this phase (git status clean throughout). Did not close sase-i8.10 or sase-i8, and did not run symvision or mark plan files done -- those belong to the sase-i8.10.land epic-closing agent per this bead's Assignee field.

## Dependencies

- **Depends on:** [sase-i8.10.3](sase-i8.10.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.10.4/README.md) | [sase-i8.10.4](sase-i8.10.4.md) | 0 |
