# Bead: sase-8v.5 — Transactional import, v1 migration, and family revival

[Bead Pages](../README.md) / [sase-8v](README.md) / sase-8v.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8v.5` · **Size:** large
**Created:** 2026-07-23 16:59:12 UTC · **Closed:** 2026-07-24 19:50:02 UTC
**Plan:** [202607/global\_agent\_hoods.md](https://github.com/sase-org/sase--plans/blob/main/202607/global_agent_hoods.md)

## Description

Validate and import hood snapshots as recoverable batches, rewrite all run relationships, preserve conditional local naming, support legacy v1 safely, and expose synced families directly to the R revival flow.

## Notes

COMMIT: 2409ed2e3

## Dependencies

- **Blocks:** [sase-8v.10](sase-8v.10.md) ✓
- **Depends on:** [sase-8v.4](sase-8v.4.md) ✓
- **Blocks:** [sase-8v.7](sase-8v.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8v.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8v.5/README.md) | [sase-8v.5](sase-8v.5.md) | 2 |
| [bbugyi200.athena.sase-8v.5--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8v.5.md#member-code) | [sase-8v.5](sase-8v.5.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@17b36ba`](https://github.com/sase-org/sase-core/commit/17b36baecd8f5b9351c6915d23f432f75af1b0ba) | feat: support transaction-gated imported agent families (sase-8v.5) | [sase-8v.5](sase-8v.5.md) | 2026-07-24 19:51:34 |
| [`2409ed2`](https://github.com/sase-org/sase/commit/2409ed2e37e454f712f44651534516d04517ef4f) | feat: import agent packages transactionally (sase-8v.5) | [sase-8v.5](sase-8v.5.md) | 2026-07-24 19:54:41 |
