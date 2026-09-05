# Bead: sase-ws.4 — Delete the import engine and v1 leg

[Bead Pages](../README.md) / [sase-ws](README.md) / sase-ws.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.y` · **Assignee:** `sase-ws.4` · **Size:** large
**Created:** 2026-09-04 13:48:30 EDT · **Closed:** 2026-09-05 13:10:05 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

## Description

delete-import-engine: delete the v2 importer, incoming cache/detection, v1 integration modules, registry import mutations, forget-import command, and ACE incomplete-import visibility gates with their tests; remove the v1_import_retired flag and close bead sase-wc; refresh shard timings.

## Notes

[2026-09-05T17:10:05Z · sase-ws.4] Implemented delete-import-engine phase: removed incoming/import runtime surfaces, closed v1_import_retired flag bead, refreshed shard timings, verified with focused suites and just check.

## Dependencies

- **Depends on:** [sase-ws.3](sase-ws.3.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-ws.5](sase-ws.5.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-ws.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-ws.4.md) | [sase-ws.4](sase-ws.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b5b3a98`](https://github.com/sase-org/sase/commit/b5b3a984f2fbe16909aa75e8007d43c35ea36681) | refactor(agents-sync): delete import engine | [sase-ws.4](sase-ws.4.md) | 2026-09-05 13:46:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-ws.4][1] | Need the assigned phase's complete description, design metadata, and notes before authoring its plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-ws.4.md

<!-- sase:referenced-by:end -->
