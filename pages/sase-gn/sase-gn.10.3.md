# Bead: sase-gn.10.3 — One snooze wake-time parser, not two

[Bead Pages](../README.md) / [sase-gn.10](sase-gn.10.md) / sase-gn.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.3` · **Size:** small
**Created:** 2026-08-07 00:13:52 EDT · **Closed:** 2026-08-07 00:36:10 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

snooze-parser-merge: collapse snooze_time.py and snooze_duration.py into a single parser so the CLI and the gate/ACE surfaces cannot accept different wake-time forms.

## Notes

[2026-08-07T04:35:51Z · sase-gn.10.3] PROPOSED FOLLOW-UP: tests/test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit flaked once under the full parallel `just check` run (passed standalone and on a rerun) — unrelated to snooze parsing, likely parallel-execution cache-path contention; worth a look if it recurs.

[2026-08-07T04:36:10Z · sase-gn.10.3] Merged snooze_duration.py into snooze_time.py as the single wake-time parser: one SnoozeTimeError, one ACCEPTED_SNOOZE_FORMS accepted-forms string (now containing 'accepted forms' for gate/ACE messages), one parse_snooze_until (duration or absolute timestamp) plus parse_snooze_request (adds the '<duration> [+<N>]' wrapper the gate/ACE need). Decided the naive-ISO-8601 behavior per the plan: attach the configured timezone rather than reject, documented in the module docstring. Updated all callers (cli_crud.py already pointed at snooze_time; snooze_gate.py, _task_gate_actions.py, _task_gate_response.py, bead_snooze_modal.py now import from snooze_time) and deleted snooze_duration.py. Updated tests/test_bead/test_snooze_gate.py and test_task_gate.py for the merged import surface, the new timezone-attach behavior (removed '2026-08-09T09:00:00' from the reject list, added a test asserting it now resolves with the configured offset), and two production-path assertions that now go through the mockable sase.core.time.local_now clock (previously real wall-clock, untestable) — both now assert against the frozen FIXED_BEAD_NOW reference. Verified: tests/test_bead/test_cli_snooze.py, test_snooze_gate.py, test_task_gate.py, and tests/ace/tui/test_bead_snooze_modal.py all green; full 'just check' green (one test_install_coverage_contexts_tool flake noted as follow-up, confirmed unrelated and non-reproducing).

[2026-08-07T04:37:00Z · sase-gn.10.3] Merged snooze_duration.py into snooze_time.py as the single wake-time parser; updated all five callers and both test modules; just check green (one unrelated flaky test noted as follow-up).

## Dependencies

- **Blocks:** [sase-gn.10.5](sase-gn.10.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.3/README.md) | [sase-gn.10.3](sase-gn.10.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`222dd1e`](https://github.com/sase-org/sase/commit/222dd1e26c9d6f579c0ceb4d97740f7e870e7dc3) | refactor(bead): merge snooze\_duration.py into snooze\_time.py as single wake-time parser | [sase-gn.10.3](sase-gn.10.3.md) | 2026-08-07 00:37:50 EDT |
