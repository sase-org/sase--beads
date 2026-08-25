# Bead: sase-tt.5 — Cut the Python-side corpus marshalling cost

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.5` · **Size:** medium
**Created:** 2026-08-25 14:59:15 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

entry-projection: stop materializing each query row three times on the Python side and shrink the per-row projection work in the agent catalog's query-entry adapter, without changing the row wire shape.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.5/README.md) | [sase-tt.5](sase-tt.5.md) | 0 |
