# Bead: sase-1dm.2 — Record context, resource usage, and pytest worker grants

[Bead Pages](../README.md) / [sase-1dm](README.md) / sase-1dm.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u4.md) · **Assignee:** `sase-1dm.2` · **Size:** medium
**Created:** 2026-09-30 16:20:07 EDT
**Plan:** [202609/tool\_stats\_demand.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_stats_demand.md)

## Description

record-demand: pin the core, capture provider and ceiling context at run start, reap the child with wait4 for CPU and max RSS, sample live tree RSS, add the SASE_TOOL_RUN_DEMAND grant channel written by tools/run_pytest, and render the record in sase tool show.

## Dependencies

- **Depends on:** [sase-1dm.1](sase-1dm.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dm.5](sase-1dm.5.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dm.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.2/README.md) | [sase-1dm.2](sase-1dm.2.md) | 0 |
