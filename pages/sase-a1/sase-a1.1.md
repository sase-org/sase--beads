# Bead: sase-a1.1 — Read the event streams as a per-bead timeline

[Bead Pages](../README.md) / [sase-a1](README.md) / sase-a1.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a1.1` · **Size:** medium
**Created:** 2026-07-27 16:34:23 UTC · **Closed:** 2026-07-27 17:22:31 UTC
**Plan:** [202607/bead\_history\_truthful\_close.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_history_truthful_close.md)

## Description

history: add a Rust replay API that turns a bead's event stream into an ordered list of field-level changes, expose it through the PyO3 binding, and ship `sase bead history` as its first reader.

## Dependencies

- **Blocks:** [sase-a1.3](sase-a1.3.md) ✓
- **Blocks:** [sase-a1.5](sase-a1.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a1.1/README.md) | [sase-a1.1](sase-a1.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3dd9765`](https://github.com/sase-org/sase/commit/3dd976565937d0b9851d25c94be1ef89442d2885) | feat(beads): add history command (sase-a1.1) | [sase-a1.1](sase-a1.1.md) | 2026-07-27 17:25:21 |
