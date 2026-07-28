# Bead: sase-9z.2 — Route every plan-reference resolver through the shared API

[Bead Pages](../README.md) / [sase-9z](README.md) / sase-9z.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9z.2` · **Size:** medium
**Created:** 2026-07-27 12:39:24 UTC
**Plan:** [202607/durable\_plan\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/durable_plan_refs.md)

## Description

resolve: replace the five independent path-guessing implementations that turn a stored reference into a file with calls into the shared resolver, so every surface agrees on what a reference means.

## Dependencies

- **Depends on:** [sase-9z.1](sase-9z.1.md) ✓
- **Blocks:** [sase-9z.3](sase-9z.3.md) ✓
- **Blocks:** [sase-9z.4](sase-9z.4.md) ✓
- **Blocks:** [sase-9z.5](sase-9z.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9z.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9z.2/README.md) | [sase-9z.2](sase-9z.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f593eca`](https://github.com/sase-org/sase/commit/f593eca04f2279b35c41e05472e21a3ca5cf3224) | feat: unify plan reference resolution across readers (sase-9z.2) | [sase-9z.2](sase-9z.2.md) | 2026-07-27 13:54:47 |
