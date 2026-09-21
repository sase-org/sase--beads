# Bead: sase-14n.15.2 — Reach and restore dismissed notifications from the notification modal

[Bead Pages](../README.md) / [sase-14n.15](sase-14n.15.md) / sase-14n.15.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-14n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.land.md) · **Assignee:** `sase-14n.15.2` · **Size:** medium
**Created:** 2026-09-21 15:11:24 EDT · **Closed:** 2026-09-21 19:12:40 EDT
**Plan:** [202609/finish\_sase\_14n\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_sase_14n_landing_leftovers.md)

## Description

dismissed_view: give the ACE notification modal a way to show dismissed rows, so its existing u binding can restore one, then advertise both keys in the footer.

## Notes

[2026-09-21T23:11:23Z · sase-14n.15.2] PROPOSED FOLLOW-UP: test_question_highlight_uses_answer_focused_footer fails on master — MagicMock footer auto-creates set_variant so footer.update is never called (call_args None); give the double a real NotificationHintFooter or set set_variant None

[2026-09-21T23:12:02Z · sase-14n.15.2] PROPOSED FOLLOW-UP: test_test_shards committed timing table drifted 21% past the 20% gate (4249 files vs measured 3513) from repo growth — run just refresh-shard-timings

[2026-09-21T23:12:40Z · sase-14n.15.2] T toggles a dismissed-only view (title 'Notifications (dismissed)') reloading via include_dismissed=True; u restores highlighted/marked rows. Verified: production-path tests seed a dismissed unread live CustomGate, open via _show_notification_modal, T, u (store undismissed, still unread), T back (row listed), Enter reaches handle_custom_gate with no mark_read (8/8 pass); footer carries T: dismissed + u: undismiss in all 3 variants at 84/108 cells with q/+1 intact; sase tool run check lints all green, 44614 passed, 18 failures each reproduced on clean master (15 pre-existing incl. question-footer MagicMock bug + shard-table drift, 3 parallel-load flakes passing in isolation). Key T chosen: no twin in use (t free), view-level like R/S. Read+dismissed rows stay out of both views (unread-scoped inbox; Rust undismiss clears dismissed only); pending bundles remain via sase gate list/show.

## Dependencies

- **Depends on:** [sase-14n.15.1](sase-14n.15.1.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.15.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.2/README.md) | [sase-14n.15.2](sase-14n.15.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a8bd795`](https://github.com/sase-org/sase/commit/a8bd795be2b80c08bfd13c098d05e8d8c3b74e2a) | feat(notifications): add dismissed view toggle and undismiss restore | [sase-14n.15.2](sase-14n.15.2.md) | 2026-09-21 19:14:31 EDT |
