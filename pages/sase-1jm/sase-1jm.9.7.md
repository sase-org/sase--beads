# Bead: sase-1jm.9.7 — Light rows carry bundle path and times, and labels show names

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.7` · **Size:** medium
**Created:** 2026-10-12 14:50:52 EDT · **Closed:** 2026-10-12 18:52:15 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

record-light-rows: carry bundle_path, stop_time, and dismissed_at on the sase-core archive light row, move the core revision pin, let bundle resolution and light-row Record use them, and show project display names instead of directory keys on light-row surfaces.

## Notes

[2026-10-12T22:25:48Z · sase-1jm.9.7] PROPOSED FOLLOW-UP: sase-core check hit known flake sase-1gz (federation_worker listener_creates_private_socket_and_rejects_symlink) — triage KNOWN, touched=false; corpus tests passed and this phase did not edit gateway IPC

[2026-10-12T22:51:55Z · sase-1jm.9.7] PROPOSED FOLLOW-UP: test_quitting_from_archive_persists_grouping_only expects grouping=project after init but gets day — reproduces on clean base; likely leftover from lazy grouping-file load in sase-1jm.9.1

[2026-10-12T22:51:56Z · sase-1jm.9.7] PROPOSED FOLLOW-UP: test_dismissed_marker still expects revive copy while production shows ▶ archive — reproduces on clean base; same as KNOWN test_neighbors_map_shows_dismissed_revive_cells (jump_opens_archive)

[2026-10-12T22:52:15Z · sase-1jm.9.7] Verified light-row bundle_path/stop_time/dismissed_at on sase-core corpus (15 corpus tests) and Python Record/CLI/facade (30 tests). Record maps PROJECT_NAME via display_snapshot; unreadable rows skip raw_suffix index I/O. No --epic-symbol leftovers. sase-core check hit known flake sase-1gz (untouched). sase check lint green, 55349 passed; 2 NEW failures (test_dismissed_marker, test_quitting_from_archive_persists_grouping_only) reproduce on clean base; other KNOWN owners sase-1ic/sase-1k4.

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.8](sase-1jm.9.8.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.7/README.md) | [sase-1jm.9.7](sase-1jm.9.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@546afe3`](https://github.com/sase-org/sase-core/commit/546afe324e268249240b9011ade13394869bce75) | feat(archive): emit bundle\_path and times on archive light rows | [sase-1jm.9.7](sase-1jm.9.7.md) | 2026-10-12 18:53:31 EDT |
| sase | [`48b31c4`](https://github.com/sase-org/sase/commit/48b31c4e432aef3a05f782044b58546f0fb6ceb7) | feat(archive): use light-row bundle path, times, and project names | [sase-1jm.9.7](sase-1jm.9.7.md) | 2026-10-12 18:58:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.7][1] | Need remaining notes, decisions, and design details | 6 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.7/README.md

<!-- sase:referenced-by:end -->
