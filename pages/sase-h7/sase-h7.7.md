# Bead: sase-h7.7 — Gate actions in the ACE modals and the plan edit round trip

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.7` · **Size:** medium
**Created:** 2026-08-07 17:08:02 EDT · **Closed:** 2026-08-07 19:27:26 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

gate-actions-ace: render an Actions section in the shared gate modals, run `edit_file` in place without tearing down the modal, point the plan and epic edit action at the durable `~/.sase/plans/` file, and block submission while an unaccepted draft exists.

## Notes

[2026-08-07T23:07:37Z · sase-h7.7] PROPOSED FOLLOW-UP: recorded_rejection only records GateError — an adapter that rejects with its own exception type (the plan adapter raises PlanApprovalValidationError) escapes errors/ and is invisible under `d`; broaden it in command_runner.py, or make GateAdapter.validate_edited_resource wrap adapter errors in GateError. Found while fixing the same too-narrow except in accept_edited_origin.

[2026-08-07T23:27:26Z · sase-h7.7] gate-actions-ace landed: GateActionControls renders an Actions section above Decision in both shared gate modals (omitted when a gate declares no actions), with declared keys rebound at render time against the reviewer's GateModalKeymaps from the shared fallback pool and the actually-bound key shown in the label and footer; actions join the modal focus ring. edit_file now runs in place — resolve_edit_path opens the durable ~/.sase/plans/ file for both plan tiers (edit_target: origin), accept_edited_origin gates it on 'sase plan validate', and the modal is never dismissed, so branch selection, toggled AND members, typed feedback and scroll position all survive. An unaccepted draft shows a banner and blocks every submit control (including reject); D discards it after confirmation via the new discard_origin_draft. run_command actions execute through the tracked task queue with streamed output, summary as a toast, body in a new GateActionOutputModal, and refresh reloading the re-verified bundle. A partial_attempt now opens GateRetryModal and resubmits with the chosen resume/restart instead of guessing. PlanApprovalResult(action='edit') and PlanApprovalModal.action_edit are deleted; legacy plan notifications keep 'e' via a synthesized action plus PlainFileEditRunner. Fixed a real defect from sase-h7.4: accept_edited_origin rolled back only on GateError, but the plan adapter rejects with PlanApprovalValidationError, so a rejected plan draft left the bundle holding unvalidated content — the rollback now catches any rejection (tests/ace/tui/test_notification_gate_actions.py proves the bundle bytes and review_revision are unchanged). Verified: just check exit 0 (every lint gate + scoped lane, 586/2424 files); new tests tests/ace/tui/test_gate_action_controls.py (11), test_gate_retry_choice.py (5), test_notification_gate_actions.py (5), plus discard_origin_draft cases in tests/test_gate_operations.py; PNG goldens custom_gate_actions_120x40 and custom_gate_draft_banner_120x40 added and the four plan-gate goldens regenerated for the footer change (just test-visual passes).

[2026-08-07T23:29:32Z · sase-h7.7] just check exit 0: all lint gates + scoped test lane (586/2424 files). Gate action controls, in-place edit round trip, draft banner/discard, run_command output modal, retry choice; 21 new tests + PNG goldens.

## Dependencies

- **Blocks:** [sase-h7.12](sase-h7.12.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.4](sase-h7.4.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.7/README.md) | [sase-h7.7](sase-h7.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a78b105`](https://github.com/sase-org/sase/commit/a78b105b5fc1055345fe9d783fe71c6d798f42ef) | feat(notification-gates): run gate actions from the ACE modals | [sase-h7.7](sase-h7.7.md) | 2026-08-07 19:30:40 EDT |
