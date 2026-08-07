# Bead: sase-gn.6 — BeadSnooze wake gate

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.6` · **Size:** medium
**Created:** 2026-08-06 19:27:57 EDT · **Closed:** 2026-08-06 21:03:13 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

snooze-wake-gate: register the bead_snooze gate kind with a close-primary, ready and re-snooze secondaries, and let a gate be born already snoozed so the wake needs no second timer.

## Notes

[2026-08-07T01:00:47Z · sase-gn.6] PROPOSED FOLLOW-UP: two load-sensitive tests flaked once each under a parallel `just check` and passed in isolation and on rerun — tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_y_recovers_workspace_from_agent_meta_json and tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget; neither touches gates.

[2026-08-07T01:01:14Z · sase-gn.6] PROPOSED FOLLOW-UP: the plan asked for BeadSnooze in the mobile priority action set in crates/sase_core/src/notifications/mobile.rs, but that file has no per-action priority list — is_priority_gate covers only PlanApproval/EpicApproval/UserQuestion/LaunchApproval and TaskTriage maps to Unsupported — so BeadSnooze mirrors TaskTriage (Python priority.py only, no core change); decide separately whether bead gates should be mobile-priority for both kinds.

[2026-08-07T01:01:44Z · sase-gn.6] PROPOSED FOLLOW-UP: the wake gate needed a pre-persistence hook, so GateAdapter gained validate_selection(selected_option_ids, feedback), called by the executor right after feedback normalization; an option command cannot see feedback text, so this is the only place a mistyped re-snooze duration can be rejected while leaving the gate pending (plan said "fails the option command").

[2026-08-07T01:02:09Z · sase-gn.6] PROPOSED FOLLOW-UP: src/sase/bead/snooze_duration.py is the shared "<duration> [+<N>]" parser the plan assigns to phases .5/.7/.8; it layers days (3d) on parse_duration, which has no day unit. _parse_snooze_until is private until the CLI phase needs a duration-only entry point.

## Dependencies

- **Depends on:** [sase-gn.4](sase-gn.4.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.7](sase-gn.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.6/README.md) | [sase-gn.6](sase-gn.6.md) | 0 |
