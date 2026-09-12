# Bead: sase-zw.5 — Bound per-project agent artifact directories

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.5` · **Size:** medium
**Created:** 2026-09-12 13:26:44 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

artifacts: give ace-run month shards a retention horizon that protects referenced and recent runs, and drop the empty out-of-range shards that starve shard watches.

## Notes

[2026-09-12T20:21:32Z · sase-zw.5] READER AUDIT: artifacts/ace-run readers checked for retention horizon - ACE Agents tab and agent index need active, recent, incomplete, and referenced runs; chat transcript lookup and named-agent lookup need retained agent names and dirs; agent prompt archives remain sidecar-backed; artifact-file rows, artifact links, beads, plans, gates, and sidecars protect producer dirs or agent refs; housekeeping keeps the newest 2 months whole and dry-run/apply blocks on protection-source gaps.

[2026-09-12T20:22:02Z · sase-zw.5] PROPOSED FOLLOW-UP: Reject future trusted launch timestamps before creating ace-run shards - retention now protects future non-empty runs and reports empty out-of-range shards for apply cleanup, but launch timestamp validation should reject future YYmmdd_HHMMSS inputs before mkdir.

## Dependencies

- **Blocks:** [sase-zw.7](sase-zw.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.5/README.md) | [sase-zw.5](sase-zw.5.md) | 0 |
