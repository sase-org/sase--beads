# Bead: sase-on.1 — Threshold config and TaskTriage suppression

[Bead Pages](../README.md) / [sase-on](README.md) / sase-on.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04x.md) · **Assignee:** `sase-on.1` · **Size:** medium
**Created:** 2026-08-17 11:47:54 EDT · **Closed:** 2026-08-17 12:38:01 EDT
**Plan:** [202608/task\_bead\_gate\_thresholds.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_gate_thresholds.md)

## Description

triage: add the grouped `bead.task_triage` config block with its three fields, schema entries, and fail-open accessors, add the shared staleness/suppression predicates, and teach the bead_task_triage chop to withhold a TaskTriage gate from a sub-threshold ready task bead and to cancel the ones it already raised.

## Notes

[2026-08-17T16:38:01Z · sase-on.1] Implemented bead.task_triage config block (min_plus_ones/stale_after_days/stale_cleanup_min_beads) with schema entries and fail-open accessors in src/sase/bead/config.py; added shared task_gate_suppressed/stale_task_bead predicates in new src/sase/bead/task_triage_policy.py; wired suppression into sase_chop_bead_task_triage.py to withhold TaskTriage gates below the +1 bar and cancel already-raised ones with reason=task_bead_below_plus_one_threshold; updated default_config.yml, schema, and docs (axe.md, beads.md, notifications.md, configuration.md). Verified: 191 targeted tests pass (task_triage_policy, config, config_schema, chop task_triage/presentation/projects/snooze, flag_triage); just check gates all pass (fmt, ruff, mypy, symvision with sase-on-keyed epic-symbol entries, toobig, validate-committed-plans, docs-check) except two pre-existing failures confirmed unrelated via git-stash diff against clean master (feature-flags lint on unrelated bead sase-om, memory init --check drift) and one flaky ace-tui test (test_logs_pane.py) confirmed passing in isolation. epic-symbols check clean for sase-on.1 (three entries correctly keyed to parent epic sase-on, not this phase).

[2026-08-17T16:38:25Z · sase-on.1] PROPOSED FOLLOW-UP: tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes fails when run as part of the full suite (just test-scoped escalated run) but passes in isolation — likely cross-test state leakage in ace-tui, similar in nature to the proc-observer thread leak fixed in commit 2959d3992; worth a focused investigation.

## Dependencies

- **Blocks:** [sase-on.4](sase-on.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-on.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-on.1/README.md) | [sase-on.1](sase-on.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b34d0d3`](https://github.com/sase-org/sase/commit/b34d0d3b6d85a821c7aac94e422e486eda77ae80) | feat(bead): withhold TaskTriage gates below a configurable +1 bar | [sase-on.1](sase-on.1.md) | 2026-08-17 12:39:35 EDT |
