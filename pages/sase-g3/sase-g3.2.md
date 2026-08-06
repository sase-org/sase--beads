# Bead: sase-g3.2 — Make the scoped lane's selection and degradation visible on the success path

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.2` · **Size:** small
**Created:** 2026-08-06 08:55:23 EDT · **Closed:** 2026-08-06 09:39:13 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

visible: `tools/run_silent` discards captured output on success, so a passing `just check` shows only `✓ test (scoped)` and hides how many tests ran, whether the run escalated, and whether the contexts baseline was missing; surface a one-line scoped summary that survives the success path.

## Notes

[2026-08-06T13:39:13Z · sase-g3.2] Implemented: manifest_summary_line() in tests/_test_selection_report.py renders the scoped lane's one-line summary (selected count/share or escalation, rules fired, contexts baseline status) from the persisted JSON manifest; tools/print_scoped_summary is the CLI wrapper wired into the Justfile check recipe as a separate step immediately after 'tools/run_silent "test (scoped)"' returns, outside run_silent's captured region, so it survives the success path. Verified: 33 new/updated unit+CLI tests pass (tests/test_test_selection_report.py, tests/test_print_scoped_summary_tool.py, tests/test_justfile_lint.py incl. two new tests pinning step order and that check-full prints nothing); all 11 just-check lint gates pass; end-to-end against the real manifest written by this diff's own (Justfile-triggered) escalated test-scoped run, tools/print_scoped_summary correctly printed 'scoped: escalated to the full suite (rules: justfile, selection-tooling); contexts baseline missing'. The escalated full-suite run had 5 failures (fakey/test_retry_pipeline_e2e.py x3, ace/tui/test_prompt_catalog.py, test_bead/test_cli_work_contention_regressions.py) that all pass individually in isolation -- pre-existing load-sensitive flakes already covered by the epic's out-of-scope flake family (sase-e2, sase-ct), not caused by this change.

## Dependencies

- **Blocks:** [sase-g3.5](sase-g3.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.2/README.md) | [sase-g3.2](sase-g3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da6105b`](https://github.com/sase-org/sase/commit/da6105b51edf8141b979478882ba6c0aa4b0a81a) | feat(test-selection): surface the scoped lane's summary on the success path | [sase-g3.2](sase-g3.2.md) | 2026-08-06 09:39:55 EDT |
