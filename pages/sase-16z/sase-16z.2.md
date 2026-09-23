# Bead: sase-16z.2 — sase-core: floors, jitter, parking, hot cadence, and reservation reads in admission

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.2` · **Size:** medium
**Created:** 2026-09-23 11:06:11 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

core-admission-policy: extend due/admit evaluation (opt-in via `adaptive` and new optional request fields) with per-provider polling floors, deterministic ±10% jitter, CLI-fingerprint unparking, and hot cadence (hot hints, warn-level windows, passive-coverage suppression). Add a `mark_provider_usage_hot` store operation, a read-only live-reservation listing, and per-provider floor-aware freshness on reads, all with bindings and golden legacy-compat tests.

## Dependencies

- **Depends on:** [sase-16z.1](sase-16z.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.5](sase-16z.5.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.2/README.md) | [sase-16z.2](sase-16z.2.md) | 0 |
