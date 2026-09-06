# Bead: sase-x7.6 — Back up and migrate local state on all three machines

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.6` · **Size:** medium
**Created:** 2026-09-05 18:55:31 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

local-state-cutover: Execute the rehearsed maintenance runbook on athena, mac, and apollo; back up quiescent state, apply the supported import-state purge, migrate remaining local stores and roots, remove verified residue without following symlinks, and produce per-host receipts before resuming compatible writers.

## Dependencies

- **Depends on:** [sase-x7.2](sase-x7.2.md) ◐ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.3](sase-x7.3.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.7](sase-x7.7.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.8](sase-x7.8.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.6/README.md) | [sase-x7.6](sase-x7.6.md) | 0 |
