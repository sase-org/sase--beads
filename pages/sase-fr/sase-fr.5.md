# Bead: sase-fr.5 — Prior-close warning in the TaskTriage gate

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.5` · **Size:** small
**Created:** 2026-08-05 21:21:22 EDT · **Closed:** 2026-08-05 23:35:32 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

triage: put a prior-close callout above the description in the task triage preview, mark the reopening +1, add the reopen badge to the notification note, and include close history in the chop's presentation fingerprint.

## Notes

[2026-08-06T03:34:50Z · sase-fr.5] PROPOSED FOLLOW-UP: three tests are timing-sensitive under full-suite parallel load and flake in `just check`/`just test-cov` (each passes standalone): tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget, tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent. Not touched by this phase; worth raising their budgets or isolating them from parallel contention.

[2026-08-06T03:35:32Z · sase-fr.5] Implemented the prior-close warning callout in the TaskTriage gate preview (task_gate.py), threaded close_history through create_task_triage_gate/_build_task_triage_gate_spec/render_task_triage_preview, added the ↺N reopen badge to task_triage_presentation_note, marked the reopening +1 evidence entry with REOPEN_EVIDENCE_MARKER, and added close_history to the chop's _presentation_fingerprint (sase_chop_bead_task_triage.py) plus full payload validation in kind_validation.py. Verified: just install + just check passing after removing 3 now-satisfied symvision --epic-symbol whitelist entries (close_history_display_order, evidence_reopened_bead, reopen_badge) from the Justfile; fmt/ruff/mypy/pyscripts/changelog/symvision/toobig all green. Full scoped test run shows 3 pre-existing failures (test_contract_set_serial_runtime_stays_within_budget, test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, test_watchdog_keeps_hitch_and_stall_state_machines_independent) that are timing-sensitive under parallel load and each pass individually in isolation — unrelated to this change, logged as a PROPOSED FOLLOW-UP note. Targeted suites all green: tests/test_bead/test_task_gate.py + tests/test_axe_chop_bead_task_triage.py (41 passed), tests/test_notification_gates.py (38 passed).

## Dependencies

- **Depends on:** [sase-fr.3](sase-fr.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.8](sase-fr.8.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.5/README.md) | [sase-fr.5](sase-fr.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`81d6191`](https://github.com/sase-org/sase/commit/81d6191e3326265822b36b7040339fba7ce1eabd) | feat(bead): warn on prior close in the TaskTriage gate | [sase-fr.5](sase-fr.5.md) | 2026-08-05 23:37:20 EDT |
