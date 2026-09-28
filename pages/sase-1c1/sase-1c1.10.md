# Bead: sase-1c1.10 — Move measurement lanes out of the release-gating Full CI

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.10` · **Size:** medium
**Created:** 2026-09-28 07:09:36 EDT · **Closed:** 2026-09-28 10:00:26 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

ci-telemetry-split: move test-cost, coverage-contexts, and contention into a new scheduled CI Telemetry workflow with realistic timeouts, run plain just test on 3.13 in Full CI, give the 3.12 coverage leg headroom, and update the coverage-contexts fetcher, workflow tests, and docs.

## Notes

[2026-09-28T14:00:01Z · sase-1c1.10--1] PROPOSED FOLLOW-UP: full-suite escalation (triggered by tests/_test_selection_contexts.py + Justfile selection-tooling changes) surfaced 18 pre-existing failures unrelated to ci-telemetry-split: tests/ace/tui/* (chrome_layout, admin_center_selection_resume, config_center_resume, log_panel_keymap, plugins_browser_pane_loading, agent_header_panel, prompts_overlay_entry_points), tests/completion/test_kind_coverage.py, tests/test_agent_artifact_marker_path_passing_audit.py, tests/test_axe_run_agent_exec_repeat_env.py (4 subtests), tests/test_config_schema_tools.py, tests/test_docs_getting_started_providers.py, tests/test_timezone_display_guard.py. Verified identically reproducing with this phases changes stashed (clean base tree) via targeted pytest runs, so they are not caused by ci-telemetry-split. No task bead filed yet -- epic land agent should triage/file.

[2026-09-28T14:00:26Z · sase-1c1.10--1] Verified ci-telemetry-split: actionlint clean on ci.yml/build-core.yml/telemetry.yml; 106 tests in test_github_actions_ci_master_gate.py/test_github_actions_ci_workflow.py/test_justfile_lint.py pass; 125 tests in the test-selection-contexts/coverage-contexts/select-tests suites pass. Full just check escalated to the full suite (49620 items) and hit 18 NEW failures across unrelated TUI/schema/docs-wording tests plus 3 KNOWN/1 FLAKY; confirmed via targeted pytest runs that the 17 reproducible ones fail identically with this phase's changes stashed (clean base tree), so they predate this phase and are not caused by it. No --epic-symbol leftovers for this phase. Recorded as PROPOSED FOLLOW-UP for epic land-agent triage.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.10.md) | [sase-1c1.10](sase-1c1.10.md) | 0 |
