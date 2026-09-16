# Bead: sase-11l.2 — Rust hold-record store and bindings

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.2` · **Size:** large
**Created:** 2026-09-15 22:46:00 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

hold-store-core: add agent_hold.rs, a TTL-bounded fail-open flock-guarded hold store under SASE home with prune-on-read, armer-liveness pruning, the match/exclusion predicate, and pyo3 bindings.

## Dependencies

- **Blocks:** [sase-11l.3](sase-11l.3.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.2.md) | [sase-11l.2](sase-11l.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4ef449d`](https://github.com/sase-org/sase-core/commit/4ef449de9fc232402fc1eee72dbd5b6199438bf7) | feat(agent-hold): add durable hold store | [sase-11l.2](sase-11l.2.md) | 2026-09-15 23:17:28 EDT |
