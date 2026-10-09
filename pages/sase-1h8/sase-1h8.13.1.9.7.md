# Bead: sase-1h8.13.1.9.7 — Shrink the over-cap read-model files and fix the stale phase-approval docs

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.7` · **Size:** small
**Created:** 2026-10-08 21:24:22 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

caps-docs: move the read-model functions that publish-direct changed out of read_model/store.rs (2,174 lines, 2,099 before the epic) and read_model/tail.rs (1,554, 1,519 before) into new files, so tail.rs is at or under 1,500 and store.rs at or under 2,099; in sase, fix the docs/beads.md sentence that still says phase agents auto-approve epic-tier plans.

## Dependencies

- **Blocks:** [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.7/README.md) | [sase-1h8.13.1.9.7](sase-1h8.13.1.9.7.md) | 0 |
