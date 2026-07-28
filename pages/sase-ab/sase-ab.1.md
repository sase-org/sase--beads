# Bead: sase-ab.1 — Restore unpushed bead-commit protection for root-layout stores

[Bead Pages](../README.md) / [sase-ab](README.md) / sase-ab.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ab.1` · **Size:** medium
**Created:** 2026-07-28 11:36:12 UTC · **Closed:** 2026-07-28 11:57:44 UTC
**Plan:** [202607/land\_beads\_sidecar\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202607/land_beads_sidecar_epic.md)

## Description

prepare: teach the workspace-preparation preflight that a repository can itself be the bead store, so local-only bead commits in the dedicated beads clone are published or rescued before a clean and hard checkout discards them.

## Notes

[2026-07-28T11:57:08Z · sase-ab.1] Implemented a shared canonical bead-state marker probe and taught workspace preparation to protect both legacy repo/beads stores and dedicated repo-root stores. Added root-layout rescue, discovery, unpushed-count, and managed-push coverage. Verified focused workspace regressions (4 passed), bead adoption regressions (5 passed), and all 71 tests from the full-suite failure set in isolation. just check passed fmt, Ruff, mypy, pyscripts, Symvision, toobig, SASE validation, and committed plans; its parallel suite had 15 cross-workspace/xdist contention failures after 22,867 passes, all of which passed in the isolated rerun.

## Dependencies

- **Blocks:** [sase-ab.5](sase-ab.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ab.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ab.1/README.md) | [sase-ab.1](sase-ab.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0ee67b1`](https://github.com/sase-org/sase/commit/0ee67b10a5e36519ffa93998a4b2969c8eca86a1) | fix(bead): protect root-layout stores during workspace prep (sase-ab.1) | [sase-ab.1](sase-ab.1.md) | 2026-07-28 12:00:20 |
