# Bead: sase-ng.1.5 — Retire the launch-body support modules the deletion orphans

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.5` · **Size:** medium
**Created:** 2026-08-17 15:16:51 EDT · **Closed:** 2026-08-17 17:50:28 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

support_retire: delete the second-order orphans the body deletion leaves behind — the background-spawn bridge, launch-history helpers, TUI workflow executor, and the ref-resolution mixin — resolving each against symvision rather than by assumption.

## Notes

[2026-08-17T21:50:07Z · sase-ng.1.5--1] PROPOSED FOLLOW-UP: just check-full test-cost budget gate failed (peak_worker_rss_kib, causes.ace_page_enter, causes.parser_create, causes.textual_app_run_test_enter all over budget+15%) despite the pytest suite itself passing cleanly (32542 passed, 13 skipped, 0 failed) and every lint/mypy/symvision gate passing. This is the pre-existing, unrelated, already-tracked infra flake in sase-j0 (just check-full is red on master on the test-cost budget gate); recorded a +1 there with this run's specifics rather than filing a new task.

[2026-08-17T21:50:28Z · sase-ng.1.5--1] Verified via just check-full (monitor 7k1psmw3d0qs): every lint/fmt/mypy/symvision gate and the full pytest suite passed cleanly (32542 passed, 13 skipped, 0 failed). The run's only failure was tools/check_test_cost_budgets — the pre-existing, already-tracked master-wide infra flake (sase-j0), unrelated to this phase's dead-code removal; recorded a +1 on sase-j0 with this run's specifics. sase bead epic-symbols sase-ng.1.5 confirms zero remaining --epic-symbol entries. Deleted _launch_background.py, _launch_history.py, _workflow_exec.py, run_workflow_runner.py, RefResolutionMixin._resolve_vcs_from_prompt, strip_all_vcs_refs, strip_known_project_vcs_refs, and the dead _bulk_changespecs compat property; renamed WorkspaceBeadEvictionRefused to _WorkspaceBeadEvictionRefused (its only external catcher was the deleted run_workflow_runner.py).

[2026-08-17T21:51:11Z · sase-ng.1.5--1] just check-full: all lint/fmt/mypy/symvision gates + full pytest suite passed (32542 passed, 13 skipped, 0 failed). Only failure was the pre-existing test-cost budget gate (peak RSS, ACE page-enter, parser-create, textual-run-test-enter over budget+15%), a known master-wide infra flake tracked in sase-j0; added +1 corroboration there instead of filing a new bead. epic-symbols confirmed zero remaining --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-ng.1.4](sase-ng.1.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-ng.1.6](sase-ng.1.6.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.1.5.md) | [sase-ng.1.5](sase-ng.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65b72d4`](https://github.com/sase-org/sase/commit/65b72d43afc9c84ed313c77592744aa3de8c86ec) | refactor(tui): retire launch-body support modules orphaned by the deletion | [sase-ng.1.5](sase-ng.1.5.md) | 2026-08-17 17:51:57 EDT |
