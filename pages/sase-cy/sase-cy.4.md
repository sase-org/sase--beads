# Bead: sase-cy.4 — End-to-end regression matrix and documentation

[Bead Pages](../README.md) / [sase-cy](README.md) / sase-cy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qu/README.md) · **Assignee:** `sase-cy.4` · **Size:** small
**Created:** 2026-08-01 10:46:08 UTC · **Closed:** 2026-08-01 12:55:14 UTC
**Plan:** [202608/reliable\_notification\_snoozing.md](https://github.com/sase-org/sase--plans/blob/main/202608/reliable_notification_snoozing.md)

## Description

regression-docs: verify state, timing, ordering, concurrency, and downstream delivery together and document the resulting guarantees and recovery behavior.

## Notes

[2026-08-01T12:54:41Z · sase-cy.4] PROPOSED FOLLOW-UP: three pre-existing test failures on clean master — tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root, ::test_write_sdd_files_rebases_seeded_parent_section, and tests/ace/tui/visual/test_ace_png_snapshots_config_center_config.py::test_config_center_config_tab_png_snapshot (config detail pane renders chop_script_dirs, golden is stale); all three reproduce with sase-cy.4 changes stashed

[2026-08-01T12:55:04Z · sase-cy.4] PROPOSED FOLLOW-UP: sase-telegram linked repo venv has a stale editable sase install, so tests/test_snooze_resurface_e2e.py skips with "installed sase predates the canonical snooze-expiry store API" — the 4 tests pass under the main workspace venv; refresh that repo venv or pin its sase dep so the e2e matrix runs in its own CI

[2026-08-01T12:55:14Z · sase-cy.4] Added tests/notification_store/test_snooze_e2e_matrix.py (state/timing/ordering/concurrency matrix) and sase-telegram tests/test_snooze_resurface_e2e.py; fixed ACE modal ordering to sort by activity key (resurfaced_at ?? timestamp) via new activity_sort_key; documented snooze expiry state transitions, timing guarantees, activity ordering, legacy/malformed deadlines, and raw-vs-current-state reads across docs/notifications.md, ace.md, integrations.md, rust_backend.md, mobile_gateway.md, mobile_mvp_runbook.md and the sase-telegram docs. Verified: 50 passed for the touched Python suites, 4 passed for the telegram e2e under the current store, just check green except three failures that reproduce on clean master (2x test_sdd_file_writes, 1x config_center_config visual golden) — recorded as follow-ups.

## Dependencies

- **Depends on:** [sase-cy.2](sase-cy.2.md) ✓
- **Depends on:** [sase-cy.3](sase-cy.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cy.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cy.4/README.md) | [sase-cy.4](sase-cy.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`7163200`](https://github.com/sase-org/sase/commit/7163200f5cd8c9793f58db6753609b66cae3ab74) | test: add snooze resurface regression matrix and document guarantees | [sase-cy.4](sase-cy.4.md) | 2026-08-01 12:55:55 |
