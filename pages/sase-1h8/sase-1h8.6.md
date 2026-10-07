# Bead: sase-1h8.6 — TUI Beads and Plans pane refresh

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.6` · **Size:** medium
**Created:** 2026-10-06 18:59:36 EDT · **Closed:** 2026-10-06 21:46:55 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

tui-board: group phases in one pass, stop forced reloads on auto-refresh ticks, and load list/ready/blocked from one core read via a board-snapshot binding.

## Notes

[2026-10-07T00:34:42Z · sase-1h8.6] tui-board done. Core: new bead/board.rs board_snapshot (one read_store_issues + ready/blocked IDs via shared in_issues helpers) + beads/board.rs bead_board_snapshot binding; read.rs helpers widened to pub(crate). Python: bead_read_facade.board_snapshot (optional binding, 3-read fallback), load_project_beads one-read lane, one-pass phases-by-parent grouping in beads_data.py, on_refresh force=False on Beads+Plans panes with on_explicit_refresh force=True (lifecycle/view/ArtifactsMixin plumbing; manual refresh, post-mutation completions, link add/remove use explicit path; auto tick stays non-forcing). Plans pane bead load already single list_issues read, no change needed there. Cold load on /tmp copy of live store (7062 issues, 2112 streams, 218MB): legacy list+ready+blocked min/med/max 1.249/1.342/1.404s; board snapshot 0.663/0.830/0.905s; single list_issues 0.660s; board parity vs separate queries OK on the copy. Unchanged-store tick performs no store read (fingerprint key decides; covered by test). No sase-core-revision.txt bump in working tree: pin update rides the host landing commit (commits sase-core sibling first), as in sase-1h8.5. -r record tui-board implementation and measurements

[2026-10-07T01:46:38Z · sase-1h8.6--1] Check triage (ToolRun bbc5394ee5e53eea3dae2cf18bc78153, exit 1, 3 NEW + 2 KNOWN): 2 TUI failures caused by this phase (test_refresh_freshness artifacts-beads param, test_link_follow remove-refresh) — production now calls _request_active_artifacts_explicit_refresh while test doubles only defined the old name; fixed by adding the explicit method to the doubles in test_refresh_freshness.py, _link_follow_helpers.py, test_refresh_panel_dispatch.py (assertions unchanged). 3rd failure (agy_usage_probe timeout test) passes in isolation on both clean base and this tree — timing-flaky under full-suite load, not caused by this change. Reran failing lane + neighbors: 80 passed.

[2026-10-07T01:46:55Z · sase-1h8.6--1] tui-board done and verified: sase-core board_snapshot core+bead_board_snapshot binding (sase-core just check green, ToolRun 2694fba1893d004e149f3853cf9c328e), cold-load legacy 3-read 1.249/1.342/1.404s vs board 1-read 0.663/0.830/0.905s. Full sase check ToolRun bbc5394ee5e53eea3dae2cf18bc78153: 3 NEW triaged — 2 TUI doubles fixed to the new explicit-refresh API (80 passed on rerun incl. neighbors), agy timeout test flaky-only-in-full-suite (passes isolated on both trees). epic-symbols clean. No commits, no revision bump.

## Dependencies

- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.5](sase-1h8.5.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.6.md) | [sase-1h8.6](sase-1h8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0506689`](https://github.com/sase-org/sase-core/commit/0506689b381e7a95eb7507becf1d149b0b829a45) | feat(core): bead board\_snapshot with single-read list/ready/blocked | [sase-1h8.6](sase-1h8.6.md) | 2026-10-06 21:48:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.6--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.6.md

<!-- sase:referenced-by:end -->
