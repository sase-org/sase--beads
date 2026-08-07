# Bead: sase-gn.9 — Cross-surface verification and documentation

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.9` · **Size:** small
**Created:** 2026-08-06 19:28:17 EDT · **Closed:** 2026-08-06 23:46:07 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

snooze-verification: exercise the whole snooze lifecycle and the indicator end to end, check both repositories' gates, update user documentation, and record the memory updates that need owner approval.

## Notes

[2026-08-07T03:42:31Z · sase-gn.9] PROPOSED FOLLOW-UP: sase/memory/sase_beads.md status list is stale — add `snoozed` (between `ready` and `in_progress`) to its Status section, matching the epic-added status now documented in docs/beads.md Status Lifecycle. Per D7 this epic deliberately does not edit memory files itself.

[2026-08-07T03:42:46Z · sase-gn.9] PROPOSED FOLLOW-UP: `sase bead list`'s default (no --status) still excludes `snoozed`, even though the design explicitly reasoned a snoozed task should not disappear like a black hole (that reasoning shipped for DEFAULT_BEAD_FILTER_QUERY in filter_query.py, but the separate hardcoded default status list in handle_bead_list at src/sase/bead/cli_query.py:66 — `[Status.OPEN, Status.CLAIMED, Status.READY, Status.IN_PROGRESS]` — was not updated to match). Confirmed via `sase bead list --help`: "List open, claimed, ready, and in-progress beads by default." `sase bead search` already includes snoozed by default; only plain `list` is inconsistent. Decide whether to add SNOOZED to that default (docs/beads.md now documents the current excluded behavior accurately).

[2026-08-07T03:50:50Z · sase-gn.9] Verified end to end against real (non-mocked) code paths in scratch SASE_HOME/bead stores, no production data touched: (1) full lifecycle — ready task raises exactly one TaskTriage gate; the gate's real snooze option settles it and raises exactly one bead_snooze gate with the notification muted+snooze_until set to the wake time; that notification lands in exactly the __snoozed__ tab; the indicator renders snoozed-only as '1z' and drops that chip (keeping it in the tooltip) once an unrelated unread notification exists; backdating snooze_until resurfaces the notification via the store's real expiry pass; ready_bead_snooze and resnooze_bead_snooze both verified correct. (2) +1 wake path — snoozing with plus_ones=2 stays snoozed after one +1, wakes with the preset 'Reopened by +1 threshold' note after the second, and the reconciler swaps the bead_snooze gate for a fresh task_triage gate. (3) multi-tag regression — a two-tag notification now occupies exactly one tab and dismissing it clears exactly one tab's count, confirming the D1 structural fix. (4) just check-full is green (fmt/lint/symvision/toobig/SASE validation/full test suite). (5) just test-visual is green at 411 passed/1 skipped after accepting one legitimate snapshot change (artifacts_beads_reopened_detail_120x40.png picked up the z-snooze keybinding footer phase 8 added); two other visual failures seen mid-run (test_real_fakey_retry_countdown, test_agents_slow_tool_calls_fold_levels) were confirmed as pre-existing contention flakes, not caused by this epic — both pass cleanly in isolation and in a final full clean run. (6) sase-core crate's own gates are clean in its own repo: cargo fmt --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace (every crate, all passing) with no changes needed. (7) Updated docs/beads.md, docs/notifications.md, and docs/ace.md for the new snoozed status, sase bead snooze, the BeadSnooze wake gate, and the indicator's per-tab chip/tooltip rules — also corrected several sections that were already stale from earlier phases (old multi-tag-tab model, old orange/gold/cyan indicator description, muted-tab-hides-snooze claims), committed as 44727b027. Two PROPOSED FOLLOW-UP notes recorded on this bead (sase_beads.md staleness per D7; sase bead list's default status set excluding snoozed inconsistently with the design's own stated intent). SEVERE FINDING recorded on the epic bead sase-gn (not here, per the DISCOVERED ISSUE convention for issues caused by an active epic): closing a snoozed task bead permanently corrupts its bead store — reproduced 3x in isolation — and this is the BeadSnooze gate's PRIMARY/default Close action, so it needs attention before this epic should be considered safe to use, let alone landed as-is.

## Dependencies

- **Depends on:** [sase-gn.3](sase-gn.3.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gn.8](sase-gn.8.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.9/README.md) | [sase-gn.9](sase-gn.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44727b0`](https://github.com/sase-org/sase/commit/44727b0275df6c62f09c7929677ce54e35f4a8a4) | docs(bead): document the snoozed task-bead status and per-tab indicator | [sase-gn.9](sase-gn.9.md) | 2026-08-06 23:46:28 EDT |
