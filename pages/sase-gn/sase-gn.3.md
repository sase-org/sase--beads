# Bead: sase-gn.3 — Per-tab notification indicator and hover briefing

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.3` · **Size:** medium
**Created:** 2026-08-06 19:27:35 EDT · **Closed:** 2026-08-06 21:43:44 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

notif-indicator: render one colored count per panel tab with the snoozed-only "<N>z" rule, bounded overflow, and a multi-line tooltip briefing, wired through every existing indicator refresh path.

## Notes

[2026-08-07T01:43:44Z · sase-gn.3] notif-indicator landed: NotificationIndicator now takes set_tabs(tabs) and renders one colored chip per panel tab in panel order, the snoozed-only '<N>z' collapse (suppressed entirely when any other tab is pending), a '+K' overflow chip bounded by ace.notification_indicator_max_counts, and a rich.text.Text hover briefing (header counting only non-snoozed/non-muted rows, per-tab colored labels, 'oldest ... ago' via format_relative_time and 'next wakes in ...' via format_relative_until, click hint). set_counts/set_count are gone. Tabs are carried on the provider snapshot (AceNotificationSnapshot.tabs and AceNotificationCountSnapshot.tabs) from the core snapshot's tabs via a new notification_tabs_from_core adapter, so no new disk read or FFI call is added; every prior set_counts site is migrated (lifecycle startup tuple now (unread_ids, cursors, tabs); all three _notification_polling sites). Verified: rewritten tests/test_notification_indicator.py (22 tests: chip count/order/color, snoozed-only and suppression, muted keeps its chip, configured and default overflow, tooltip mixed/snoozed-only/empty, an indicator-vs-panel one-to-one invariant against classify_notification_modal_tabs, and a guard that the widget's locally-spelled __snoozed__/__muted__ keys match the modal's), updated toast-polling and startup tests to assert per-tab counts (incl. the now-distinct Snoozed tab), and just check green with the full suite (26602 passed). just test-visual: the badge change is intentional, so the visual startup fixture now supplies two tabs (hitl 1, general 18) and 408 PNG goldens were regenerated with --sase-update-visual-snapshots; suite re-run clean at 411 passed. Dropped three now-consumed sase-gn.3 --epic-symbol entries from the Justfile.

[2026-08-07T01:44:20Z · sase-gn.3] Per-tab indicator + hover briefing; just check green (full suite escalation), visual goldens regenerated and just test-visual green.

## Dependencies

- **Depends on:** [sase-gn.2](sase-gn.2.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.9](sase-gn.9.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.3/README.md) | [sase-gn.3](sase-gn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`09bb443`](https://github.com/sase-org/sase/commit/09bb443ea4206edf188b54042713cf561fc89f94) | feat(ace-tui): show one indicator chip per notification tab | [sase-gn.3](sase-gn.3.md) | 2026-08-06 21:45:00 EDT |
