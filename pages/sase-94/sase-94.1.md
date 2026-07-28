# Bead: sase-94.1 — Claim retry and project-scoped store recovery

[Bead Pages](../README.md) / [sase-94](README.md) / sase-94.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-94.1` · **Size:** medium
**Created:** 2026-07-25 11:36:49 UTC
**Plan:** [202607/claimed\_bead\_publication\_race.md](https://github.com/sase-org/sase--plans/blob/main/202607/claimed_bead_publication_race.md)

## Description

'Claim retry and project-scoped store recovery' section: add a project-scoped read-recovery bead-store refresh and rebuild the waiting-agent claim around a bounded retry budget that survives a not-yet-integrated store and bead-mutation lock contention.

## Notes

COMMIT: d1f9609c7

## Dependencies

- **Blocks:** [sase-94.3](sase-94.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-94.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-94.1/README.md) | [sase-94.1](sase-94.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a8b63c2`](https://github.com/sase-org/sase/commit/a8b63c27f0fb89b04f4bd214b556685925bd39f4) | fix(beads): recover waiting claims after publication lag (sase-94.1) | [sase-94.1](sase-94.1.md) | 2026-07-25 12:14:12 |
