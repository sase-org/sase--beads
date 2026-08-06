# Bead: sase-fr.6 — ACE beads pane close history

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.6` · **Size:** small
**Created:** 2026-08-05 21:24:29 EDT · **Closed:** 2026-08-05 23:30:10 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

ace: show the reopen badge on beads list rows, a Previously closed property and body section in the detail pane, and a has:reopened filter, with PNG snapshot coverage.

## Notes

[2026-08-06T03:29:34Z · sase-fr.6] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout and tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget are timing/contention-sensitive and fail intermittently under `just check`'s full parallel test-scoped run in this sandbox, but both pass standalone (uv run pytest <test> -p no:xdist). Not caused by this phase (no lock/contract-manifest code touched); worth tightening their budgets/timeouts or isolating them from contended parallel runs.

[2026-08-06T03:30:10Z · sase-fr.6] Added the ↺N reopen badge to beads list rows (beads_rendering.py), a Previously closed property + ## Previously Closed body section to the detail pane (beads_detail.py), and a has:reopened filter + close_history search text (beads_filtering.py + filter_query.py's BEAD_HAS_VALUES). Verified: uv run pytest across tests/ace/tui/test_artifacts_beads_{rendering,filtering,loading,mutations,navigation}.py and tests/test_bead/ (1443 passed), the beads PNG visual suite including a new artifacts_beads_reopened_detail_120x40 golden (6 passed), and just lint clean (dropped the now-satisfied sase-fr epic-symbol whitelist entries in Justfile since close_history_display_order/close_history_search_text/close_record_label/close_record_reopened_label/reopen_badge now have real consumers; evidence_reopened_bead stays whitelisted for the still-pending cli/triage phases). just check's full test-scoped run has 2 unrelated timing-sensitive failures that pass standalone; recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-fr.3](sase-fr.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.8](sase-fr.8.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.6/README.md) | [sase-fr.6](sase-fr.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4130721`](https://github.com/sase-org/sase/commit/413072167f8069fb0b6714075897358cb9920e78) | feat(ace): show bead close history in the beads pane | [sase-fr.6](sase-fr.6.md) | 2026-08-05 23:32:32 EDT |
