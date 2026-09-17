# Bead: sase-124.5 — Remove Agents-tab UI-thread hitches (unread ack, info-panel countdown)

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.5` · **Size:** medium
**Created:** 2026-09-17 10:59:45 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

ui-hitches: move the unread-ack notification-store mutation off the UI thread with optimistic row updates, and make the 1 s info-panel countdown patch only the countdown segment.

## Dependencies

- **Blocks:** [sase-124.7](sase-124.7.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.5.md) | [sase-124.5](sase-124.5.md) | 0 |
