# Bead: sase-14n.13 — Make notification dismissal recoverable

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.13` · **Size:** medium
**Created:** 2026-09-20 17:14:22 EDT · **Closed:** 2026-09-20 20:20:16 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

gate_undismiss: add an undismiss state transition to the notification action surfaces so a dismissed live gate can be reached again.

## Notes

[2026-09-21T00:19:26Z · sase-14n.13--1] PROPOSED FOLLOW-UP: tests/ace/tui/test_feature_flags_pane_journeys.py::test_flags_pane_enable_and_disable_write_state_and_request_restart flaked under full-lane load (5s wait_for restart timeout) then passed in isolation in 11s; unrelated to notification undismiss diff

[2026-09-21T00:20:16Z · sase-14n.13--1] undismiss round trip verified: Rust parity notification_undismiss_restores_dismissed_rows green (63 passed), 105 focused pytest passes (tests/notification_store/, modal undismiss/tab-order), full check lane 13772 passed with 1 unrelated flags-pane flake that passes in isolation (11s), just lint green, no epic-symbols left

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.3](sase-14n.3.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.13.md) | [sase-14n.13](sase-14n.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`98bf83a`](https://github.com/sase-org/sase/commit/98bf83a38cc9f51e97465e09faeff47c33d5c865) | feat(notifications): add undismiss transition to recover dismissed live gates | [sase-14n.13](sase-14n.13.md) | 2026-09-20 20:22:42 EDT |
