# Bead: sase-1q2.6 — Run Full CI on a tip with every fix and repair what is still red

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Assignee:** `sase-1q2.6` · **Size:** medium
**Created:** 2026-10-30 12:37:07 EDT · **Closed:** 2026-10-31 04:36:11 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

full-ci: run Full CI on a tip containing every sibling fix, then fix each remaining deterministic red, including the toobig split if its routine has not landed it.

## Notes

[2026-10-31T08:36:02Z · sase-1q2.6--1] CI triage and proof for the full-ci phase.

Qualifying Full CI: run 41174188852 on dd72e6d78a60d74bfc62e48af6bc6ddd55b7fc02 completed failure. Master Gate at that SHA: run 41174126199 completed failure. Expected schedule-only skips were release-core-floor-smoke and docs-build. Full CI failed test (3.12), test (3.13), test (3.14), lint, and visual-test; Master Gate failed test (2), test (6), and lint.

Prerequisite phases are included in current master: core matcher deb8bb60b6aa1a159324fb3491f2ec69eedbf945; CLI reds 3f9fe9c1079dd3862b2f176b2fff0b525b5ca337; TUI reds e28334c45a72ec02d10b0564b06909f6d14751bf; harness reds dab2d701fbac135ff3e828b2d0efd330c5a19b47. The oversized monitor-test split landed as 211158db707d4251a3421af06d20a2b1b7ddb0bd; tests/monitor/test_monitor_start_stage.py is now 68 lines, down from the CI-reported 1163.

Fixed deterministic reds with no live agent owner:
- tests/agents_sync/test_cli_names.py::test_repair_states_dispatches_and_reports_json raised NameError because handle_agents_sync was not imported. Added the import. Existing task sase-1q7 tracks this failure and remains open; only this phase bead is being closed. Node passed 20/20 serial runs; changed file passed 3/3 runs with -n 8.
- tests/ace/tui/widgets/test_prompt_format.py::test_newer_format_request_wins had a fake formatter that self-released after an unasserted 2-second wait, letting the old result race the newer request under load. The fake now blocks until explicit release and finally releases on test exit. Node passed 20/20 serial runs; changed file passed 3/3 runs with -n 8.

Remaining CI reds were non-reproducible in current-master checks:
- test_bump_microbench_stays_within_two_microseconds reported 2.276 us on Master Gate and 2.603 us / 11.116 us on Full CI; it passed 20/20 serial local runs. PROPOSED FOLLOW-UP: investigate runner-dependent variance in this benchmark without changing its 2 us bound.
- test_reveal_matches_fresh_home[pairs1-] failed on Python 3.13 and 3.14 with a prompt subtitle mismatch; current Python 3.14 passed 20/20 serial runs. PROPOSED FOLLOW-UP: investigate the platform/timing-dependent prompt-bar reveal mismatch.
- visual-test timed out in test_agents_stranded_resolve_modal_png_snapshot with load_task pending and reported drift for agents_final_rows_80x40 and capacity-inspector snapshots. Current-master targeted visual check passed 13 tests, reported 12 unchanged snapshots, zero created/updated, and the stranded-modal case passed on recapture after one unstable attempt. Existing task sase-1nx already tracks the final-row snapshot flake. PROPOSED FOLLOW-UP: investigate the stranded-modal convergence timeout and capacity-inspector drift if either reproduces.

Current master is dcee7f11e9342935619dfbd85d670c7dfff1c98e. just fix passed. sase tool run check passed on the current tip as ToolRun f3bc890263d39e7d1c865eb0ec1e1188 (scoped tests succeeded). epic-symbols reported no leftovers.

[2026-10-31T08:36:11Z · sase-1q2.6--1] Full CI 41174188852 on dd72e6d failed; Master Gate 41174126199 also failed. Fixed deterministic CLI NameError and formatter race, with 20 serial node passes and 3 x -n 8 per changed file. Current-master just fix and ToolRun f3bc890263d39e7d1c865eb0ec1e1188 passed. The line-cap split is on master; remaining perf, prompt-bar, and visual failures were not reproducible and are recorded as PROPOSED FOLLOW-UPs. epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1q2.1](sase-1q2.1.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q2.3](sase-1q2.3.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q2.4](sase-1q2.4.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q2.5](sase-1q2.5.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q2.7](sase-1q2.7.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.6.md) | [sase-1q2.6](sase-1q2.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eec20f6`](https://github.com/sase-org/sase/commit/eec20f6ad54e295575f0f1e736527d656e84143c) | fix(tests): stabilize CI regression tests | [sase-1q2.6](sase-1q2.6.md) | 2026-10-31 04:37:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:16a--1][1] | Check whether the active full-CI phase owns the stale Symvision closed-epic whitelist failure | 1 |
| read-by | [agent:toobig-8x.agent_loader_artifacts.0][2] | Need the in-progress full CI repair phase scope before routing check evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16a.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-8x.agent_loader_artifacts.0/README.md

<!-- sase:referenced-by:end -->
