# Bead: sase-9z.5 — Validate and repair stored plan links

[Bead Pages](../README.md) / [sase-9z](README.md) / sase-9z.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9z.5` · **Size:** large
**Created:** 2026-07-27 12:39:40 UTC · **Closed:** 2026-07-27 15:12:51 UTC
**Plan:** [202607/durable\_plan\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/durable_plan_refs.md)

## Description

doctor: make the health check actually check plan links, add an opt-in repair that rewrites legacy paths to canonical references using the plan `bead_id` reverse index, and migrate the live store.

## Dependencies

- **Depends on:** [sase-9z.1](sase-9z.1.md) ✓
- **Depends on:** [sase-9z.2](sase-9z.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9z.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9z.5/README.md) | [sase-9z.5](sase-9z.5.md) | 2 |
| [bbugyi200.athena.sase-9z.5--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-9z.5.md#member-code) | [sase-9z.5](sase-9z.5.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@b5c37cc`](https://github.com/sase-org/sase-core/commit/b5c37cc7404bcbc9a95868dad61e576a1151bc70) | feat(beads): validate doctor plan references (sase-9z.5) | [sase-9z.5](sase-9z.5.md) | 2026-07-27 15:16:21 |
| [`7ac5b91`](https://github.com/sase-org/sase/commit/7ac5b917c08ebe10f847caacdcabf2a2fcc401a6) | feat(beads): repair legacy design references (sase-9z.5) | [sase-9z.5](sase-9z.5.md) | 2026-07-27 15:18:08 |
