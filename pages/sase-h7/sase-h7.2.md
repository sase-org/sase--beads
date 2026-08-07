# Bead: sase-h7.2 — One feedback-to-input rule for every surface

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.2` · **Size:** medium
**Created:** 2026-08-07 17:07:08 EDT · **Closed:** 2026-08-07 17:41:41 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

feedback-input: replace ACE's never-copy, mobile's option-id heuristic, and Telegram's required-list heuristic with one shared helper that injects the reviewer's note as `input.feedback` whenever the selected option's schema declares a `feedback` property, after auditing every built-in schema.

## Notes

[2026-08-07T21:41:41Z · sase-h7.2] Added src/sase/notification_gates/feedback_input.py (labelled compatibility shim with deletion trigger) implementing the one rule: the reviewer note is injected as input.feedback iff the selected option's input_schema declares a feedback property. Applied it inside execute_gate_selection so every caller (ACE, mobile, Telegram, headless) shares it; deleted the mobile bridge's 'feedback' in selected_option_ids heuristic and ACE's hardcoded input_data={}. Audited built-in schemas: launch_request_gate and plan_gate feedback options declare the property (injection matches what their surfaces already assembled); workflow HITL, task triage, and snooze options do not, so their empty-input commands are untouched. Verified: new tests/test_gate_feedback_input.py (7 tests incl. required-feedback fails with feedback_required before any command runs) + new mobile bridge test, 1681 gate/notification/plan/launch/snooze/triage tests pass, and 'just check' is fully green (all lint gates + scoped tests). Telegram's feedback_is_command_input() deletion stays scheduled in sase-h7.8 (inputs-remote), which owns that repo.

## Dependencies

- **Blocks:** [sase-h7.11](sase-h7.11.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.8](sase-h7.8.md) ◎ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.2/README.md) | [sase-h7.2](sase-h7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e184090`](https://github.com/sase-org/sase/commit/e18409056355a8013772060644e6381426d74364) | refactor(gates): one feedback-to-input rule for every surface | [sase-h7.2](sase-h7.2.md) | 2026-08-07 17:43:33 EDT |
