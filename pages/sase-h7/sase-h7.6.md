# Bead: sase-h7.6 — Generic typed input collection in the ACE gate modals

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.6` · **Size:** large
**Created:** 2026-08-07 17:07:56 EDT · **Closed:** 2026-08-07 21:36:23 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

inputs-ace: extract the typed-field form out of `InputCollectionModal` into a reusable widget and render each selected option's declared inputs inside `GateBranchControls`, so plan, epic, custom, triage, and snooze gates all collect input with no per-kind code.

## Notes

[2026-08-08T01:16:20Z · sase-h7.6] PROPOSED FOLLOW-UP: pre-existing (pre-dates this phase, reproduces on clean master) failures found while running just check for inputs-ace: tests/test_gate_cli_show.py::test_show_json_reports_declared_inputs_branches_and_actions, test_show_prints_a_readable_summary_of_the_decision_surface, test_show_reports_the_terminal_status_of_an_answered_gate, test_show_reports_a_cancelled_gate; and tests/gate_conformance/test_gate_conformance.py::test_gate_conformance[cli-legacy_shared_input] / [ace-legacy_shared_input]. Same root cause already noted by sase-h7.10 and sase-ha.1: the sase-h7.5 creation-time answerability check (_validate_option_answerability) now rejects these fixtures' options, which declare a required schema property (reason/ticket) without declaring it under inputs:. Corroborating a third time so the epic's land agent has independent confirmation across three unrelated phases before promoting it to a task. Verified pre-existing via git stash back to a clean checkout before filing this note.

[2026-08-08T01:36:23Z · sase-h7.6] Implemented gate_inputs_ace_1.md in full: TypedInputForm extracted, GateBranchControls renders declared inputs with raw-schema escape hatch, option_inputs threaded through custom/plan submission paths, ACE conformance gap closed. Verified this session: all 7 just check-full lint gates pass; full suite 27311 passed with 6 failures (test_gate_cli_show.py x4, gate_conformance cli/ace-legacy_shared_input) confirmed pre-existing by reproducing identically on clean master with changes stashed; gate_conformance matrix run directly shows previously-skipped ACE per-option cases (divergent_option_inputs, every_input_type, feedback_plus_input, no_input, feedback_only, partial_attempt) now passing, remaining skips all belong to sase-h7.8 (mobile); just test-visual 559 passed with only the pre-existing frontmatter_panel_raw_diagnostics failure (also reproduced on clean master), including the new custom_gate_inputs_120x45 golden and unchanged inputs/prompt_inputs goldens.

## Dependencies

- **Blocks:** [sase-h7.11](sase-h7.11.md) ◐ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.3](sase-h7.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-h7.6.md) | [sase-h7.6](sase-h7.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e1da6d1`](https://github.com/sase-org/sase/commit/e1da6d1b76fd1ea28bc620ab20ad63085842e932) | feat(notification-gates): collect typed gate inputs in the ACE modals | [sase-h7.6](sase-h7.6.md) | 2026-08-07 21:37:07 EDT |
