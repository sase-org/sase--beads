# Bead: sase-14d.4 — Apply rules in the notification poll

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.4` · **Size:** medium
**Created:** 2026-09-20 13:11:34 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

tui-delivery: resolve each arriving notification's delivery on the existing worker hop, filter toast-suppressed rows out before batching, and play at most one resolved sound per poll tick in place of the unconditional tmux bell.

## Dependencies

- **Depends on:** [sase-14d.1](sase-14d.1.md) ◐ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.2](sase-14d.2.md) ◐ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.3](sase-14d.3.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.5](sase-14d.5.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.4/README.md) | [sase-14d.4](sase-14d.4.md) | 0 |
