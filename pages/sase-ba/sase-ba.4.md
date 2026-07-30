# Bead: sase-ba.4 — Retroactive version-control reclaim of the pooled bytes

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.4

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.4` · **Size:** medium
**Created:** 2026-07-30 14:40:49 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

py-reclaim: add `sase artifact reclaim`, which converts stored automatic rows whose exact content is reproducible from a durable ref into byte-free VCS-backed rows and trashes the redundant copies, reusing the capture policy's git probe and verifying by digest first.

## Dependencies

- **Depends on:** [sase-ba.3](sase-ba.3.md) ✓
- **Blocks:** [sase-ba.6](sase-ba.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.4/README.md) | [sase-ba.4](sase-ba.4.md) | 0 |
