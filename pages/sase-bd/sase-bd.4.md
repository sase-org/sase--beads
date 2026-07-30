# Bead: sase-bd.4 — An honest sase bead close command

[Bead Pages](../README.md) / [sase-bd](README.md) / sase-bd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.4` · **Size:** medium
**Created:** 2026-07-30 17:44:44 UTC · **Closed:** 2026-07-30 18:58:30 UTC
**Plan:** [202607/bead\_close\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity.md)

## Description

cli-close: stop printing "Closed" for beads that were already closed, distinguish cascade closes from requested ones, make the auto-commit message name what actually happened, and stop the default resolution from manufacturing a conflict on every commit-hook close.

## Notes

[2026-07-30T18:58:30Z · sase-bd.4] Verified 119 focused CLI/golden/hook tests and the full just check suite; repeat closes are truthful no-ops, note-only closes use note commits, conflicts preserve store bytes, and cascade rows/commit IDs are honest.

## Dependencies

- **Depends on:** [sase-bd.2](sase-bd.2.md) ✓
- **Blocks:** [sase-bd.7](sase-bd.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.4/README.md) | [sase-bd.4](sase-bd.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`5f682e2`](https://github.com/sase-org/sase/commit/5f682e2b1b0ebb7fb295c8cffef49ba495c70f8c) | fix(beads): report close mutation outcomes honestly | [sase-bd.4](sase-bd.4.md) | 2026-07-30 18:59:42 |
