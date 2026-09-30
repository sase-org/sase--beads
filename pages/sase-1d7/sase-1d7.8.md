# Bead: sase-1d7.8 — Read-free ack completion and a coalescing ack writer

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.8` · **Size:** medium
**Created:** 2026-09-30 07:18:17 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

ack-pipeline: delete the synchronous post-ack store read, apply ack outcomes to the cached snapshot by id, schedule only the guarded async resync, and drain queued acks through one coalescing worker that issues one Rust call per batch.

## Dependencies

- **Blocks:** [sase-1d7.12](sase-1d7.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.7](sase-1d7.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.9](sase-1d7.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.8/README.md) | [sase-1d7.8](sase-1d7.8.md) | 0 |
