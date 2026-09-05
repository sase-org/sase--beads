# Bead: sase-ws.3 — One explicit purge for imported local state

[Bead Pages](../README.md) / [sase-ws](README.md) / sase-ws.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.y` · **Assignee:** `sase-ws.3` · **Size:** medium
**Created:** 2026-09-04 13:48:28 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

## Description

purge-local-state: generalize the v1 forget-import cleanup into one explicit command that purges all locally materialized imported state (artifacts, bundles, journals, caches, receipts, import-origin registry rows) plus a doctor check that reports leftovers.

## Dependencies

- **Depends on:** [sase-ws.2](sase-ws.2.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-ws.4](sase-ws.4.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-ws.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-ws.3/README.md) | [sase-ws.3](sase-ws.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a216ed`](https://github.com/sase-org/sase/commit/2a216eda9158cd57ed903d02e9ede93140f0753b) | feat(agents-sync): add purge-local-state command for incoming agent caches | [sase-ws.3](sase-ws.3.md) | 2026-09-05 11:22:21 EDT |
