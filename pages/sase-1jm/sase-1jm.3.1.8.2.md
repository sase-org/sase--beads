# Bead: sase-1jm.3.1.8.2 — Controller robustness, parent seams, and project display names

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.2` · **Size:** medium
**Created:** 2026-10-11 19:18:51 EDT · **Closed:** 2026-10-11 21:33:21 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

controller-seams: stop off-thread probe errors from wedging the Archive controller. Drain a queued explicit open on idle, and coalesce overlapping idle rebuilds. Publish a typed found/owner/missing arrival outcome and clear unmatched exact names. Add the restored-row overlay seam with invalidation, and keep list option IDs unique. Show PROJECT_NAME on project banners through the project display snapshot.

## Notes

[2026-10-12T01:33:06Z · sase-1jm.3.1.8.2--1] PROPOSED FOLLOW-UP: just check NEW test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data (Project: tmp vs sase) reproduces on clean HEAD 1b837fa132; same root cause as KNOWN test_project_shown_when_no_patch — already tracked by sase-1k4 (project_display_label prefers project_file-derived key over meta_project since df61663204). 5 other just check failures are KNOWN (sase-1ic import budget; project/suggest help+completion; agents_sync bounded drain flake).

[2026-10-12T01:33:21Z · sase-1jm.3.1.8.2--1] Controller seams landed: worker errors publish unavailable and unwedge idle; queued explicit open drains on idle; overlapping idle rebuilds coalesce; typed found/owner/missing arrival from the request snapshot with pending-name clear on miss; restored-row overlay with query-change and exit invalidation (sase-1jm.5(mark_archive_row_restored)); unique list option IDs for legacy rows; project banners use PROJECT_NAME via off-thread display snapshot (keys stay raw). request_archive_lookup deleted. Targeted tests 98 passed (archive controller/list/view/column + display audit). just check 798b55252753c4c90c4a1f938ec02420: 1 NEW + 5 KNOWN; NEW reproduces on clean HEAD and is sase-1k4. No leftover --epic-symbol for this phase.

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.8.2.md) | [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb46ff6`](https://github.com/sase-org/sase/commit/fb46ff6f72a0b8b567ea10cf3504977f039f9062) | fix(tui): harden Archive controller seams and show project names | [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) | 2026-10-11 21:35:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.8.2--1][1] | Need phase notes and remaining work after failed check | 2 |
| read-by | [agent:sase-1jm.3.1.8.5][2] | remaining-proof needs prior phase evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.8.2.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.5/README.md

<!-- sase:referenced-by:end -->
