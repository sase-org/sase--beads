# Bead: sase-1jm.3.1.8.3 — Live-key toasts, read isolation, marks, footer, help, and info row

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.3` · **Size:** medium
**Created:** 2026-10-11 19:18:52 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

action-boundary-fixes: make live-only keys reach their Archive guards so they toast instead of being silently swallowed. Stop copy readers from falling back to the parked Inbox agent, and guard or route the remaining unaudited Inbox actions. Render Archive marks and refresh the footer after mark and cursor changes. Remove the nonfunctional Enter read hint, fix the overflowing help row, and gate help and leader chrome on the beta. Fix the info row's color, key label, and resize alignment (the cause of the flaky missing-index golden), and the exception chip drop order.

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) ◐ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.3/README.md) | [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) | 0 |
