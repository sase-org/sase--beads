# Bead: sase-x7.13 — Isolate immutable bead history decoding

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.13` · **Size:** medium
**Created:** 2026-09-05 18:55:37 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

historical-codec: Keep the minimal writer-free decoder required by existing append-only bead note events inside Rust historical replay, remove the Python implementation and live-input normalization, and verify identical full replay, note identities, current projections, and history queries. Do not rewrite committed event history.

## Dependencies

- **Depends on:** [sase-x7.12](sase-x7.12.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.14](sase-x7.14.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.13/README.md) | [sase-x7.13](sase-x7.13.md) | 0 |
