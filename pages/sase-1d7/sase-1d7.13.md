# Bead: sase-1d7.13 — Notification store retention and wait-check payload diet

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.13` · **Size:** large
**Created:** 2026-09-30 07:18:24 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

notification-store-diet: shorten live retention of dismissed rows and bound wait_checks plus_ones and action_data so every full read, rewrite and lock window scales with a much smaller store.

## Dependencies

- **Depends on:** [sase-1d7.12](sase-1d7.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.2](sase-1d7.2.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.13/README.md) | [sase-1d7.13](sase-1d7.13.md) | 0 |
