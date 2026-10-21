# Bead: sase-1nf.10.1.4 — Load expensive inventory data only for requested hoods

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.4` · **Size:** medium
**Created:** 2026-10-20 15:40:52 EDT · **Closed:** 2026-10-20 21:19:55 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

inventory-scope: filter indexed, dismissed, and historical records before payload hydration or per-commit Git calls, reuse commit records within a drain, and prove selected-hood equivalence.

## Notes

[2026-10-21T01:19:36Z · sase-1nf.10.1.4--2] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget fails 3526 vs cap 3524 on clean HEAD 2df906dd57 and this tree (tools/tui_import_closure --diff merge-base: +0 sase.* after deferring inventory_scope off the TUI import path); already tracked by sase-1ic

[2026-10-21T01:19:41Z · sase-1nf.10.1.4--2] PROPOSED FOLLOW-UP: tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning fails identically on clean HEAD 2df906dd57 with last_error "could not restore deferred prompt archive for alice.athena.worker@aaaaaaaaaaaa: prompt archive is unresolved and a missing local source does not prove there was no prompt obligation"; ToolRun 92f2d6a7b24fc900b7acbc9105c3f352 labeled NEW touched=false (26 agents / 7 workspaces); no owner bead found

[2026-10-21T01:19:55Z · sase-1nf.10.1.4--2] inventory-scope: optional requested_hoods filters indexed/dismissed/historical records before payload hydration and per-marker Git; empty set is a no-op; commit drains and publish_agent_hood pass selected hoods; history SHAs reused and remaining marker lookups cached per (repo, sha); scoped vs full hood snapshots match on live/legacy/dismissed/commit-only/session-lane fixtures with spies proving unrelated payloads and markers are not opened. Verified: tests/agents_sync/test_inventory_scope.py plus inventory/history/commit-publication (34 passed), mypy, symvision, just fix, tui_import_closure +0 vs HEAD after deferring inventory_scope. Remaining just check NEW items reproduce on clean HEAD 2df906dd57 (TUI import 3526 vs 3524 = sase-1ic; tagged-commit deferred prompt archive) and are recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1nf.10.1.3](sase-1nf.10.1.3.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.5](sase-1nf.10.1.5.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.4.md) | [sase-1nf.10.1.4](sase-1nf.10.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1f107c4`](https://github.com/sase-org/sase/commit/1f107c4a891953fc02c2276e1ae27c18002d5a61) | feat(agents-sync): scope inventory hydration to requested hoods | [sase-1nf.10.1.4](sase-1nf.10.1.4.md) | 2026-10-20 21:36:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.4--3][1] | Need phase status, notes, and whether work already landed | 1 |
| read-by | [agent:sase-1nf.10.1.6][2] | Identify whether the recurring prompt archive failure has an existing owner before recording a follow-up | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.6/README.md

<!-- sase:referenced-by:end -->
