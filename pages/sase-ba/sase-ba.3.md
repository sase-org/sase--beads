# Bead: sase-ba.3 — Dry-run-first pruning and the trash lifecycle

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.3

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.3` · **Size:** medium
**Created:** 2026-07-30 14:40:18 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

py-prune: add `sase artifact prune` (dry run unless `--apply`) and the `sase artifact trash {list,purge,restore}` group, with index-row removal and restoration performed under the existing index lock and every removal routed through the trash.

## Dependencies

- **Depends on:** [sase-ba.2](sase-ba.2.md) ✓
- **Blocks:** [sase-ba.4](sase-ba.4.md) ◐
- **Blocks:** [sase-ba.5](sase-ba.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.3/README.md) | [sase-ba.3](sase-ba.3.md) | 0 |
