# Bead: sase-17y.4 — Core pin bump, git-backed regressions, and incident cleanup

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.4` · **Size:** small
**Created:** 2026-09-24 11:57:15 EDT · **Closed:** 2026-09-24 13:54:41 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

pin-regression: move sase-core-revision.txt past the core-winner commit, add git-backed regressions where the local creation is older than the upstream one, and repoint the tool_handoff flag registry entry to sase-17w if it still names sase-17v.

## Notes

[2026-09-24T17:54:41Z · sase-17y.4] pin-regression done: sase-core-revision.txt bumped 9956773->6d0d0e6 (core-winner commit, = remote HEAD); added git-backed older-local regression test_duplicate_top_level_creations_older_local_still_relocates and sync-level incident mirror test_incident_older_local_creation_relocates_leaving_published_bead_stable (both pass; full tests/test_bead 2392 passed); registry already maps tool_handoff to sase-17w and sase-17v no longer exists so no cleanup edit needed; epic-symbols clean. NOTE: sase tool run check red on pre-existing mypy errors in untouched files src/sase/core/wait_dependency_resolution/_index_queries.py and src/sase/axe/run_agent_wait_deps.py (last touched by 9bd351b67), unrelated to this phase.

## Dependencies

- **Depends on:** [sase-17y.1](sase-17y.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17y.3](sase-17y.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.4/README.md) | [sase-17y.4](sase-17y.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2164ed`](https://github.com/sase-org/sase/commit/f2164ed241db6bc9c6c5b85d995f4d4c6981bf1a) | test(bead): pin core-winner core and add older-local relocation regressions | [sase-17y.4](sase-17y.4.md) | 2026-09-24 13:56:02 EDT |
