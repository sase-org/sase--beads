# Bead: sase-ud.13.1.3 — Retire the notification and family status overrides

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.3` · **Size:** large
**Created:** 2026-08-27 08:49:06 EDT · **Closed:** 2026-08-28 08:56:37 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

status-strip: delete the notification-driven pending-plan and question status overrides and the `_agent_status_overrides` facade, strip the family policy and synthetic-planner modules to what the gate shell left reachable, and prove the family node still shows the gate's status without them.

## Notes

[2026-08-27T15:51:55Z · sase-ud.13.1.3] Planning evidence measured at a646bdaf6 before proposing the sub-epic. (1) R-B does not reproduce: a plan/question family built from real gate-shell member metadata already renders the gate's status on the container (TALE/EPIC/QUESTION pending; TALE APPROVED/FEEDBACK/PLAN REJECTED/ANSWERED settled) with the planner member at DONE, and it does so through _mirror_root_from_child, NOT through concrete_agent_statuses -- which does still filter gate shells via row_is_family_shell. The grandparent plan 202608/gate_shells.md §8 is wrong about the mechanism and right about the outcome; that filter must not be changed. (2) The grandparent's "What this deletes" table is stale: it lists active_approved_plan_handoff_status and done_handoff_status as deletions, but both label concrete post-approval coder rows the gate shell does not replace (settled gate + running coder still needs WORKING TALE; + completed coder still needs TALE DONE), and neutralizing them fails 25 and 12 tests respectively. (3) The app-level _agent_status_overrides map is NOT deletable in this epic: _prompt_bar_submit.py writes RUNNING and _notification_question_modal.py writes ANSWERED into it, neither retired here. _agent_pre_question_status IS fully deletable -- one writer, all other sites are pops, no site reads the saved status back. (4) In status_buckets.py only WORKING_PLAN_STATUS_TO_APPROVED is already unreferenced; PENDING_PLAN_REVIEW_STATUSES, ACTIVE_PLAN_HANDOFF_STATUSES, APPROVED_PLAN_STATUSES and WORKING_PLAN_STATUSES all keep consumers outside the deleted passes.

## Dependencies

- **Depends on:** [sase-ud.13.1.2](sase-ud.13.1.2.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-ud.13.1.4](sase-ud.13.1.4.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) | [sase-ud.13.1.3](sase-ud.13.1.3.md) | 0 |
