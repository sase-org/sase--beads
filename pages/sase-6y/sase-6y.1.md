# Bead: sase-6y.1 — Rust core agent run statistics engine

[Bead Pages](../README.md) / [sase-6y](README.md) / sase-6y.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6y.1`
**Created:** 2026-07-18 22:32:05 UTC
**Plan:** [202607/statistics\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202607/statistics_tab.md)

## Description

'Rust core agent run statistics engine' section: add an agent_stats module to sase_core that aggregates per-run records from the agent artifact index over a caller-supplied time range (outcomes, provider/model/effort, commits, plan/question counters from run metadata, runtime grouped by tribe/clan/family/agent/provider/model/workflow, time-bucketed run counts), with wire types, PyO3 bindings, and Rust tests.

## Notes

COMMIT: d17be7b

## Dependencies

- **Blocks:** [sase-6y.2](sase-6y.2.md) ✓
- **Blocks:** [sase-6y.3](sase-6y.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6y.1/README.md) | [sase-6y.1](sase-6y.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@d17be7b`](https://github.com/sase-org/sase-core/commit/d17be7bbdd9a62769d36d2420c8eb73948c8464b) | feat(agent-stats): add run statistics aggregation (sase-6y.1) | [sase-6y.1](sase-6y.1.md) | 2026-07-18 22:51:12 |
