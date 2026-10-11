# Bead: sase-1jm.3.1.4 — View toggles, scoped filters, parking, and Archive chrome

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.4` · **Size:** medium
**Created:** 2026-10-10 20:21:21 EDT · **Closed:** 2026-10-11 02:02:37 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

query-parking: implement the pure ,a toggle, Open Archive and Back to Inbox palette actions, complete per-view parking, scoped FilterBar completion and preview, query-history and saved-slot routing, Inbox-only last-query persistence, and the persisted Archive grouping picker. Add the Archive info row and Agents marker, hide the Inbox header in Archive, and test startup, toggle, edit cancellation, scope errors, history, slots, and both agents_unified_query states.

## Notes

[2026-10-11T06:02:37Z · sase-1jm.3.1.4] Implemented Archive view presentation and Inbox state restoration, query profile/history/saved-slot routing, grouping persistence and selection, and Archive palette/context actions. Verification: focused Archive/filter tests passed (43 tests); command availability/catalog/scaffold tests passed (75 tests); Ruff passed; git diff --check passed; epic-symbol check found no remaining entries. The prior full check failures outside this phase were recorded on the parent bead, with five reproduced on clean HEAD.

## Dependencies

- **Depends on:** [sase-1jm.3.1.3](sase-1jm.3.1.3.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.3.1.5](sase-1jm.3.1.5.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.4/README.md) | [sase-1jm.3.1.4](sase-1jm.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5349e04`](https://github.com/sase-org/sase/commit/5349e046cdad8356bc382d65f87f30f910cb777b) | feat(ace): add Agents Archive view | [sase-1jm.3.1.4](sase-1jm.3.1.4.md) | 2026-10-11 02:03:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.3][1] | See sibling concurrent phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.3/README.md

<!-- sase:referenced-by:end -->
