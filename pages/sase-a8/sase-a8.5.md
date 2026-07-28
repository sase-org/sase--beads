# Bead: sase-a8.5 — Repo-root bead store layout

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a8.5` · **Size:** medium
**Created:** 2026-07-27 19:46:46 UTC · **Closed:** 2026-07-27 21:31:22 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

rootstore: support a bead store whose files live at the repository root, covering the beads dirname constant, gitignore patterns, conflict-resolver prefix handling, bead location resolution, and the project-root and bead-directory heuristics.

## Notes

[2026-07-27T21:31:14Z · sase-a1.land] [2026-07-27T20:56:12Z · sase-a8.5] (restored 2026-07-27) Implemented repository-root bead stores: root dirname/location/init handling, prefix-aware gitignore rules, safe root conflict classification, sidecar/project/discovery heuristics, commit-hook detection, and regression coverage. Verification: focused subsystem suite 155 passed; full just check passed before the final public-helper production wiring; final fmt/Ruff/mypy/pyscripts/Symvision/toobig stages passed and affected store/adoption suite 79 passed. A final just check rerun stopped only on unrelated global provider skill-shim drift reported by init skills --check.

## Dependencies

- **Depends on:** [sase-a8.1](sase-a8.1.md) ✓
- **Depends on:** [sase-a8.3](sase-a8.3.md) ✓
- **Blocks:** [sase-a8.6](sase-a8.6.md) ✓
- **Blocks:** [sase-a8.7](sase-a8.7.md) ✓
- **Blocks:** [sase-a8.8](sase-a8.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.5/README.md) | [sase-a8.5](sase-a8.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5cf149c`](https://github.com/sase-org/sase/commit/5cf149c1f5c2a914c1df0a98a63bd7d02fad5b81) | feat(beads): support repository-root bead stores (sase-a8.5) | [sase-a8.5](sase-a8.5.md) | 2026-07-27 20:58:04 |
