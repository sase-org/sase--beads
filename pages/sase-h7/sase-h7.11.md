# Bead: sase-h7.11 — Retire free-text smuggling from snooze, triage, and launch

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.11` · **Size:** medium
**Created:** 2026-08-07 17:08:24 EDT · **Closed:** 2026-08-07 22:26:46 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

retire-smuggling: express snooze durations as declared `enum`/`line` inputs, delete the two `validate_selection` re-parsing special cases, and drop the launch gate's fake `feedback` option id now that feedback is an ordinary input field.

## Notes

[2026-08-08T02:24:43Z · sase-h7.11] PROPOSED FOLLOW-UP: The feedback_input.py shim could not be deleted — retiring the smuggling built-ins removed structured data from the note, not the note itself. Still relying on the injection: plan_gate feedback options, launch reject, both bead gates deferral reason, and every custom gate with a feedback mode. Its module docstring now states the revised deletion trigger (a surface collecting the note as an ordinary declared input).

[2026-08-08T02:25:29Z · sase-h7.11] PROPOSED FOLLOW-UP: Pre-existing red on master (reproduced by stashing this phase) — tests/test_gate_cli_show.py (4 tests) and tests/gate_conformance legacy_shared_input (cli+ace) fail because their audit/legacy fixtures declare a raw required input_schema property with no matching inputs, which custom-validation phase sase-h7.5 answerability check now rejects at create_gate. Fix: declare the property under inputs in the fixture, or drop it from required.

[2026-08-08T02:26:17Z · sase-h7.11] PROPOSED FOLLOW-UP: Two more pre-existing failures unrelated to this epic, both confirmed on a stashed tree — tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand (Muse auth hint text drift) and tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot.

[2026-08-08T02:26:46Z · sase-h7.11] Retired all three smuggling paths. Snooze/triage: the wake time is now a declared enum(4h/1d/3d/7d/custom)+line custom_duration input on each gate;the command resolves and echoes it as its result, so a typo fails the command and leaves the gate pending (proven by new tests asserting errors/*.json and no response.json). Deleted validate_bead_snooze_feedback, validate_task_triage_feedback, and GateAdapter.validate_selection plus its only executor call site. Both kind validations now rebuild each option through GateOption.from_mapping so the declared inputs cannot drift. Snooze feedback is now optional and records the deferral reason. Launch: deleted the fake `feedback` option id, its command resource, the query branch, and the reject->feedback rewrite; `feedback` is a declared input on `reject` and reject+note still reports status "feedback". Legacy readers kept for in-flight bundles (execute_launch_gate_command and launch_request_response feedback branches), commented as legacy-only. feedback_input.py shim retained and re-documented (see PROPOSED FOLLOW-UP). Updated docs/notifications.md and docs/axe.md paragraphs this change falsified. Verified: just lint clean; just check green apart from 6 failures reproduced on a stashed tree (see PROPOSED FOLLOW-UP); just test-visual 559 passed with the one pre-existing frontmatter failure.

[2026-08-08T02:27:46Z · sase-h7.11] Verifying close publication

## Dependencies

- **Blocks:** [sase-h7.12](sase-h7.12.md) ◐ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.2](sase-h7.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.6](sase-h7.6.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.8](sase-h7.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.11/README.md) | [sase-h7.11](sase-h7.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`27d04a6`](https://github.com/sase-org/sase/commit/27d04a679981f65c9efb655df8518da1731f2bf6) | feat(notification-gates)!: retire free-text smuggling from snooze, triage, and launch | [sase-h7.11](sase-h7.11.md) | 2026-08-07 22:29:07 EDT |
