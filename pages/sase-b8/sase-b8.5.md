# Bead: sase-b8.5 — Lane-keyed commit history in the sidecar inventory

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.5` · **Size:** medium
**Created:** 2026-07-30 14:32:48 UTC · **Closed:** 2026-07-30 16:02:28 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

inventory: read lane-tagged commit history, keep solo attribution unchanged, route family-lane commits to the family container, stop fabricating phantom runs, and keep import evidence matching.

## Notes

[2026-07-30T16:02:28Z · sase-b8.5] Verified just lint, exact Symvision, git diff --check, and 50 focused lane/inventory/publication/import tests. Full suite reached 24,293 passed and 7 skipped; its only 2 failures are unrelated artifact-query wire skew (Python expects schema 2, linked sase_core_rs reports 3). just check also reached unrelated plans-sidecar prompt-link validation errors for three existing July plan/prompt pairs.

## Dependencies

- **Depends on:** [sase-b8.2](sase-b8.2.md) ✓
- **Depends on:** [sase-b8.4](sase-b8.4.md) ✓
- **Blocks:** [sase-b8.8](sase-b8.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.5/README.md) | [sase-b8.5](sase-b8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`eefd432`](https://github.com/sase-org/sase/commit/eefd432bab1b6562947545e0f1c52a67ea48c5a3) | feat(agents-sync): attribute commit history to agent lanes | [sase-b8.5](sase-b8.5.md) | 2026-07-30 16:04:23 |
