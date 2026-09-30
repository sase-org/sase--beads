# Bead: sase-1d7.6 — One batched unread chrome helper with no full rebuilds

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.6` · **Size:** medium
**Created:** 2026-09-30 07:18:14 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

unread-chrome-helper: route every unread change through one helper that patches only visible changed rows via an identity map, skips collapsed panels, never falls back to a full rebuild, and refreshes titles, info panel, machine chip/tab strip and tribe summary once each.

## Dependencies

- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.7](sase-1d7.7.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.8](sase-1d7.8.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.9](sase-1d7.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.6/README.md) | [sase-1d7.6](sase-1d7.6.md) | 0 |
