# Bead: sase-a9.4 — Lane neighbors on agent and family pages

[Bead Pages](../README.md) / [sase-a9](README.md) / sase-a9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a9.4` · **Size:** medium
**Created:** 2026-07-27 20:35:49 UTC · **Closed:** 2026-07-27 21:21:03 UTC
**Plan:** [202607/agent\_page\_artifacts.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_page_artifacts.md)

## Description

neighbors: build the name-derived lane kinship projection for a hood snapshot and render the Neighbors section with ancestor, descendant, and hood-group rows that link to their pages.

## Notes

[2026-07-27T21:20:50Z · sase-a9.4] Implemented snapshot-scoped lane kinship projections and shared Neighbors rendering for agent/family pages, including family-lane suppression, deterministic ancestor/descendant/hood grouping, state summaries, 50-row group caps, roster tails, relative links, focused tests, and refreshed publication goldens. Verification: just test tests/agents_sync (136 passed); just lint passed after Symvision visibility cleanup; full just test reached 22815 passed/7 skipped with one AF_UNIX temp-path-length failure, and that exact test passed with a short --basetemp. just check passed fmt, Ruff, mypy, pyscripts, Symvision, and toobig before unrelated workspace-global sase validate drift (missing configured beads sidecar and stale generated provider skill copies).

## Dependencies

- **Depends on:** [sase-a9.1](sase-a9.1.md) ✓
- **Blocks:** [sase-a9.5](sase-a9.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a9.4/README.md) | [sase-a9.4](sase-a9.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f9064d7`](https://github.com/sase-org/sase/commit/f9064d7630ca8b542f2d01323cc81ba3e3a380d6) | feat(agents-sync): add lane neighbor sections (sase-a9.4) | [sase-a9.4](sase-a9.4.md) | 2026-07-27 21:23:00 |
