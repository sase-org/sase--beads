# Bead: sase-6k.3 — Local ingestion pipeline

[Bead Pages](../README.md) / [sase-6k](README.md) / sase-6k.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6k.3`
**Created:** 2026-07-17 15:25:45 UTC
**Plan:** [202607/telemetry\_inhouse\_graphs.md](https://github.com/sase-org/sase--plans/blob/main/202607/telemetry_inhouse_graphs.md)

## Description

'Local ingestion pipeline' section: replace prometheus_client accumulation and Pushgateway/exposition egress with in-house accumulators that flush batches to the core store; enable telemetry by default and drop the prometheus_client dependency.

## Notes

COMMIT: 84ef71ce9

## Dependencies

- **Depends on:** [sase-6k.1](sase-6k.1.md) ✓
- **Blocks:** [sase-6k.4](sase-6k.4.md) ✓
- **Blocks:** [sase-6k.5](sase-6k.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6k.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6k.3/README.md) | [sase-6k.3](sase-6k.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7ccc468`](https://github.com/sase-org/sase/commit/7ccc4688c393478423072db4d7d045ed0f869b19) | feat(telemetry)!: replace Prometheus ingestion with local storage (sase-6k.3) | [sase-6k.3](sase-6k.3.md) | 2026-07-17 16:53:13 |
