# Bead: sase-1h8.4 — One parse, one validation, no lockless-read deletes

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.4` · **Size:** medium
**Created:** 2026-10-06 18:59:33 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

parse-once: in sase-core, move the removed-flag stream prune off the read path, drop the deep clone of every stream, and validate each event and issue once (~480 ms to ~290 ms per replay).

## Dependencies

- **Blocks:** [sase-1h8.7](sase-1h8.7.md) ◐ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.8](sase-1h8.8.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.4/README.md) | [sase-1h8.4](sase-1h8.4.md) | 0 |
