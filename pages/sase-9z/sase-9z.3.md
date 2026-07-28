# Bead: sase-9z.3 — Persist plans references on new beads

[Bead Pages](../README.md) / [sase-9z](README.md) / sase-9z.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9z.3` · **Size:** small
**Created:** 2026-07-27 12:39:29 UTC · **Closed:** 2026-07-27 14:10:18 UTC
**Plan:** [202607/durable\_plan\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/durable_plan_refs.md)

## Description

write: make every writer of a bead's plan link emit the canonical `plans:` form, in both the Python epic-creation path and the Rust `bead create` path.

## Dependencies

- **Depends on:** [sase-9z.1](sase-9z.1.md) ✓
- **Depends on:** [sase-9z.2](sase-9z.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9z.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9z.3/README.md) | [sase-9z.3](sase-9z.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b3a4bc2`](https://github.com/sase-org/sase/commit/b3a4bc282b0fd04bc849797b00dd0d8570282cef) | fix(bead): persist canonical plan references (sase-9z.3) | [sase-9z.3](sase-9z.3.md) | 2026-07-27 14:15:15 |
