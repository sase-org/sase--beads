# Bead: sase-xe.5 — Bounded remote read protocol with recoverable events

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.5` · **Size:** large
**Created:** 2026-09-06 14:06:42 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

gateway-reads: serve maintained resolved summaries, bounded catalog pages, batch followed-ID lookups, lazy detail, and content handles over versioned HTTP/JSON by calling the core scan/index in-process, and make the SSE stream actually deliver post-connect invalidations through a broadcast channel with a generation-plus-sequence cursor and an explicit resync path.

## Dependencies

- **Blocks:** [sase-xe.10](sase-xe.10.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.4](sase-xe.4.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.5/README.md) | [sase-xe.5](sase-xe.5.md) | 0 |
