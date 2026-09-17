# Bead: sase-124.5 — Remove Agents-tab UI-thread hitches (unread ack, info-panel countdown)

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.5` · **Size:** medium
**Created:** 2026-09-17 10:59:45 EDT · **Closed:** 2026-09-17 14:17:27 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

ui-hitches: move the unread-ack notification-store mutation off the UI thread with optimistic row updates, and make the 1 s info-panel countdown patch only the countdown segment.

## Notes

[2026-09-17T18:17:27Z · sase-124.5--1] Verified Agents-tab unread ack persistence runs off-thread with optimistic row rollback on failure, info-panel countdown ticks patch cached text without full rebuilds, focused pytest passes, and just check passes.

## Dependencies

- **Blocks:** [sase-124.7](sase-124.7.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.5.md) | [sase-124.5](sase-124.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`980de14`](https://github.com/sase-org/sase/commit/980de1487a7d6a38cf360155327d664011081cbf) | fix(tui): remove agents tab read ack hitches | [sase-124.5](sase-124.5.md) | 2026-09-17 14:19:26 EDT |
