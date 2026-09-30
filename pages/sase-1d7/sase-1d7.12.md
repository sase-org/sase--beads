# Bead: sase-1d7.12 — Rust ack API, lean unread index, and store generations

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.12` · **Size:** large
**Created:** 2026-09-30 07:18:22 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

core-unread-ack-index: move completion acks and the unread completion index into sase_core as lean GIL-released calls that return dismissed ids and a store generation, then replace the Python read-sequence fence with store generations.

## Dependencies

- **Blocks:** [sase-1d7.13](sase-1d7.13.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.2](sase-1d7.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.8](sase-1d7.8.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.9](sase-1d7.9.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.12/README.md) | [sase-1d7.12](sase-1d7.12.md) | 0 |
