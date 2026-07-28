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
