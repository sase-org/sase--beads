# Bead: sase-h7.10 — Show the input a gate asks for and the input it received

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.10` · **Size:** small
**Created:** 2026-08-07 17:08:18 EDT · **Closed:** 2026-08-07 20:41:11 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

surface-input: render declared and submitted input in the gate detail pane and Gate Debug, and add `input`, `option_inputs`, `option_results`, and executed actions to `sase gate wait --json`.

## Notes

[2026-08-08T00:31:20Z · sase-h7.10] PROPOSED FOLLOW-UP: pre-existing (pre-dates this phase, reproduces on master) failures found while running just check for surface-input: tests/test_gate_cli_show.py::test_show_json_reports_declared_inputs_branches_and_actions, test_show_prints_a_readable_summary_of_the_decision_surface, test_show_reports_the_terminal_status_of_an_answered_gate, test_show_reports_a_cancelled_gate; and tests/gate_conformance/test_gate_conformance.py::test_gate_conformance[cli-legacy_shared_input] / [ace-legacy_shared_input]. The conformance failures both raise GateError unanswerable_option for options[0] (id apply) requiring ticket without declaring it under inputs -- looks like the legacy_shared_input conformance case fixture was not updated for the custom-validation (sase-h7.5) answerability check. Not touched by sase-h7.10; verified pre-existing via git stash on a clean checkout before filing this note.

[2026-08-08T00:41:11Z · sase-h7.10] Implemented surface-input: gate detail pane (ACE) and Gate Debug now render declared vs submitted input (option inputs table + new Journal tab), and 'sase gate wait --json' includes input, option_inputs, option_results, and executed actions. just check: all lint gates pass; test-scoped has 6 pre-existing failures (test_gate_cli_show.py x4, gate_conformance legacy_shared_input x2) confirmed unrelated via git stash on clean master and already recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-h7.12](sase-h7.12.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.3](sase-h7.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.4](sase-h7.4.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.10/README.md) | [sase-h7.10](sase-h7.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a1cc172`](https://github.com/sase-org/sase/commit/a1cc172d337957f2d68d42ec9fe6c3187907ae87) | feat(notification-gates): surface declared and submitted gate input | [sase-h7.10](sase-h7.10.md) | 2026-08-07 20:41:46 EDT |
