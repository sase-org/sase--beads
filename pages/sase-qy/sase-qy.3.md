# Bead: sase-qy.3 — Persistent query bar on Plan and every document provider

[Bead Pages](../README.md) / [sase-qy](README.md) / sase-qy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07r](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07r.md) · **Assignee:** `sase-qy.3` · **Size:** medium
**Created:** 2026-08-19 10:02:25 EDT · **Closed:** 2026-08-19 14:04:57 EDT
**Plan:** [202608/artifacts\_persistent\_query\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_persistent_query_bar.md)

## Description

documents: make PlanFilterBar persistent for the Plan pane and every `ref:<kind>` provider pane, surface deep-archive coverage in the idle status lane, and delete the now-unused filter-token echo from the shared scope renderer.

## Notes

[2026-08-19T18:04:30Z · sase-qy.3] PROPOSED FOLLOW-UP: just check test-scoped is flaky under full-suite xdist parallel load — two separate runs on this tree each failed a different, unrelated test (tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet with a lingering sase-artifacts-project-choices task; tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_stays_open_when_submit_collides with a 5s modal-wait timeout). Both pass cleanly in isolation and on a clean master checkout without this phase's changes; likely CPU-contention/timing sensitivity in a handful of tests when the full 3213-item suite runs at 4 workers. Worth a dedicated flake bead investigating timeout margins in src/sase/ace/testing/wait.py-based assertions and the artifacts-project-choices task lifecycle under app teardown.

[2026-08-19T18:04:57Z · sase-qy.3] PlanFilterBar is now PERSISTENT with DISPLAY_ID=plan-filter-display, giving Plan and every ref:<kind> document-provider pane a permanently visible query bar with click-to-open editing. build_shell_scope no longer accepts filter_tokens (removed, not just unused); plans_options._scope_text and build_plans_scope dropped the header token echo accordingly. Added _sync_query_bar() funnel in PlansOptionsMixin so the idle bar's text/status/coverage stay truthful across entry-jump clears, project-scope changes, and async deep-archive results. Verification: ruff format/check, mypy, symvision, and all lint gates pass; the 43 tests directly covering this change (test_artifacts_plans_filtering, test_artifacts_shell, test_plan_filter_bar, test_ace_png_snapshots_artifacts_plans) pass cleanly in isolation, all 6 affected PNG goldens (5 regenerated + 1 renamed narrowed_filter_bar replacing narrowed_filter_chips) were visually inspected before acceptance. just check's full 3213-test scoped run hit 1-2 unrelated flaky failures across two runs (different test each time, both pass in isolation and on clean master) — logged as a PROPOSED FOLLOW-UP note on this bead, not attributable to this phase's changes.

## Dependencies

- **Depends on:** [sase-qy.2](sase-qy.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qy.4](sase-qy.4.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.3/README.md) | [sase-qy.3](sase-qy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`be757ca`](https://github.com/sase-org/sase/commit/be757cabcb363fb07c15565ec0c2864433201386) | feat(ace): make the Plan query bar persistent across document providers | [sase-qy.3](sase-qy.3.md) | 2026-08-19 14:05:52 EDT |
