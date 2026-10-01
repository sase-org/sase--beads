# Bead: sase-1dr.3 — Generic git file-history index in sase-core

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.3` · **Size:** medium
**Created:** 2026-09-30 19:09:20 EDT · **Closed:** 2026-09-30 20:18:42 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

file-history: add sase-core `file_history`. It runs a bounded, lock-free git runner and parses a first-parent `--raw -M` log over explicit pathspecs. It builds rename-aware lineage and path aliases, updates incrementally by tip ancestry, detects shallow or incomplete history, reads blobs in batches, reports a path's worktree, index, and tracked state, and persists a serializable snapshot.

## Notes

[2026-10-01T00:18:02Z · sase-1dr.3] PROPOSED FOLLOW-UP: sase tool run check stays red on clippy-1.95 nonminimal_bool/manual_range_contains in 9 untouched files (already tracked by task bead sase-1an); file_history itself is clippy-clean

[2026-10-01T00:18:42Z · sase-1dr.3] sase_core::file_history landed with wire/runner/parser/lineage/index/blobs/status plus 36 tests; all 36 pass and full sase_core lib suite is 4227 green; fmt-check and features pass; module is clippy-clean. Full sase tool run check stays red only on 9 pre-existing clippy-1.95 lints in untouched files tracked by sase-1an (noted as follow-up). No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-1dr.4](sase-1dr.4.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.3/README.md) | [sase-1dr.3](sase-1dr.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a031ee4`](https://github.com/sase-org/sase-core/commit/a031ee4fe9e887a4563f2a6748b4b277ce5a21ed) | feat(file-history): generic git file-history index in sase-core | [sase-1dr.3](sase-1dr.3.md) | 2026-09-30 20:20:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.3/README.md

<!-- sase:referenced-by:end -->
