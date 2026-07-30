# Bead: sase-6k.1 — Rust core metric store and query engine

[Bead Pages](../README.md) / [sase-6k](README.md) / sase-6k.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6k.1`
**Created:** 2026-07-17 15:25:35 UTC
**Plan:** [202607/telemetry\_inhouse\_graphs.md](https://github.com/sase-org/sase--plans/blob/main/202607/telemetry_inhouse_graphs.md)

## Description

'Rust core metric store and query engine' section: add a SQLite-backed metric sample store with delta ingestion, instant/range queries, rollups, and retention to sase-core; expose it through sase_core_rs bindings and release a 0.5.x wheel.

## Notes

COMMIT: 646cb0c

## Dependencies

- **Blocks:** [sase-6k.3](sase-6k.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6k.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6k.1/README.md) | [sase-6k.1](sase-6k.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@646cb0c`](https://github.com/sase-org/sase-core/commit/646cb0c51f30d2e6995e3544846daae7f9292f0e) | feat(telemetry): add SQLite metric store and queries (sase-6k.1) | [sase-6k.1](sase-6k.1.md) | 2026-07-17 16:15:36 |
