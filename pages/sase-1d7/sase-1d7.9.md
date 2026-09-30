# Bead: sase-1d7.9 — Cheap unread jumps and footer probe

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.9` · **Size:** medium
**Created:** 2026-09-30 07:18:18 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

unread-jump-fast-path: drop the unconditional trailing tab refresh from the unread jump keys, keep detail behind the debounce, reveal only the target panel, make the footer probe O(1), and key the jump-candidate cache by generations with remove-on-ack.

## Dependencies

- **Blocks:** [sase-1d7.12](sase-1d7.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.8](sase-1d7.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.9/README.md) | [sase-1d7.9](sase-1d7.9.md) | 0 |
