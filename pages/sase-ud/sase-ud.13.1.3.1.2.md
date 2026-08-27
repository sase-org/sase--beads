# Bead: sase-ud.13.1.3.1.2 — Retire the notification-driven status writes

[Bead Pages](../README.md) / [sase-ud.13.1.3.1](sase-ud.13.1.3.1.md) / sase-ud.13.1.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) · **Assignee:** `sase-ud.13.1.3.1.2` · **Size:** medium
**Created:** 2026-08-27 11:52:53 EDT · **Closed:** 2026-08-27 13:29:39 EDT
**Plan:** [202608/status\_strip.md](https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md)

## Description

notification-strip: delete the pending-plan and `UserQuestion` override writes in `_notification_status_overrides.py`, decide the external-response reconciliation against the gate executor's own dismissal, remove the now-writerless `_agent_pre_question_status` map, and delete the `models/_agent_status_overrides.py` re-export facade.

## Notes

[2026-08-27T17:29:04Z · sase-ud.13.1.3.1.2] VERDICTS: deleted _apply_notification_status_overrides and its pending PlanApproval/EpicApproval plus UserQuestion override writes because gate-shell metadata and pending_question markers now publish those statuses. Kept prepare_plan_notification_reconciliation and _prepare_external_plan_response only as legacy response-file/marker lifecycle compatibility: neutral gate responses are ignored because notification_gates.executor._settle_gate_notification marks handled and dismissed for terminal gate transitions. Deleted _agent_pre_question_status across production/tests because no writer remains; ANSWERED continues through _agent_status_overrides until loader reconciliation clears it. Deleted models/_agent_status_overrides.py facade; callers now import _agent_status_apply, _agent_status_diff, _agent_status_family/_core, and _agent_status_roles directly.

[2026-08-27T17:29:39Z · sase-ud.13.1.3.1.2] Verified retired notification status writers and pre-question map; neutral gates are handled by executor dismissal; focused pytest suite passed (75 tests) and just check passed.

## Dependencies

- **Depends on:** [sase-ud.13.1.3.1.1](sase-ud.13.1.3.1.1.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-ud.13.1.3.1.3](sase-ud.13.1.3.1.3.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.3.1.2/README.md) | [sase-ud.13.1.3.1.2](sase-ud.13.1.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a771258`](https://github.com/sase-org/sase/commit/a771258edf6e815bb05995918c070b6f3da19c55) | refactor(tui): retire notification status overrides | [sase-ud.13.1.3.1.2](sase-ud.13.1.3.1.2.md) | 2026-08-27 13:32:21 EDT |
