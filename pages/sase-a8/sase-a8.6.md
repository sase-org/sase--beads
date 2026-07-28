# Bead: sase-a8.6 — Commit, push, lock, and attribution routing

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Size:** medium
**Created:** 2026-07-27 19:46:54 UTC · **Closed:** 2026-07-27 21:22:55 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

commit: route bead commits, pushes, locks, health checks, agent env vars, and commit attribution to the beads repository instead of the plans repository.

## Notes

[2026-07-27T21:22:35Z · sase-a8.6] Implemented three-way plans/research/beads commit partitioning, target-repository pushes with semantic bead-dir conflict replay, split-beads agent env and runtime routing coverage, beads commit/TUI attribution, and lock/health isolation. Verification: 172 focused and replay tests pass; full suite reached 22,815 passed with one replay regression, which was fixed and then verified via the failing test plus the full remote-push module. just check passes formatting, ruff, mypy, pyscripts, symvision, and size gates; validation remains blocked only by the epic's not-yet-run beads sidecar initialization and generated provider skill refresh (future init/migration phases).

## Dependencies

- **Blocks:** [sase-a8.10](sase-a8.10.md) ✓
- **Depends on:** [sase-a8.3](sase-a8.3.md) ✓
- **Depends on:** [sase-a8.5](sase-a8.5.md) ✓
- **Blocks:** [sase-a8.8](sase-a8.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.6/README.md) | [sase-a8.6](sase-a8.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3dba997`](https://github.com/sase-org/sase/commit/3dba997d0c80ce4ec8234d650514ae50eff838a0) | feat(sdd): route bead operations to dedicated sidecar (sase-a8.6) | [sase-a8.6](sase-a8.6.md) | 2026-07-27 21:24:31 |
