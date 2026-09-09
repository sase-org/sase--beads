# Bead: sase-yy.4 — Automatic link writes publish as events through the machine lane

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.4` · **Size:** large
**Created:** 2026-09-09 11:48:17 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

event-publisher: behind a new beta flag, automatic writers enqueue events instead of dirtying agent sidecar clones, and a serialized per-project publisher batches them into the hidden host-owned clones through the existing commit choke point so the sase-yh retry ledger owns push retry.

## Dependencies

- **Depends on:** [sase-yy.3](sase-yy.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.6](sase-yy.6.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.4/README.md) | [sase-yy.4](sase-yy.4.md) | 0 |
