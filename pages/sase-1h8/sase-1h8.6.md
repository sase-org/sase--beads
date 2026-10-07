# Bead: sase-1h8.6 — TUI Beads and Plans pane refresh

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.6` · **Size:** medium
**Created:** 2026-10-06 18:59:36 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

tui-board: group phases in one pass, stop forced reloads on auto-refresh ticks, and load list/ready/blocked from one core read via a board-snapshot binding.

## Notes

[2026-10-07T00:34:42Z · sase-1h8.6] tui-board done. Core: new bead/board.rs board_snapshot (one read_store_issues + ready/blocked IDs via shared in_issues helpers) + beads/board.rs bead_board_snapshot binding; read.rs helpers widened to pub(crate). Python: bead_read_facade.board_snapshot (optional binding, 3-read fallback), load_project_beads one-read lane, one-pass phases-by-parent grouping in beads_data.py, on_refresh force=False on Beads+Plans panes with on_explicit_refresh force=True (lifecycle/view/ArtifactsMixin plumbing; manual refresh, post-mutation completions, link add/remove use explicit path; auto tick stays non-forcing). Plans pane bead load already single list_issues read, no change needed there. Cold load on /tmp copy of live store (7062 issues, 2112 streams, 218MB): legacy list+ready+blocked min/med/max 1.249/1.342/1.404s; board snapshot 0.663/0.830/0.905s; single list_issues 0.660s; board parity vs separate queries OK on the copy. Unchanged-store tick performs no store read (fingerprint key decides; covered by test). No sase-core-revision.txt bump in working tree: pin update rides the host landing commit (commits sase-core sibling first), as in sase-1h8.5. -r record tui-board implementation and measurements

## Dependencies

- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.5](sase-1h8.5.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.6.md) | [sase-1h8.6](sase-1h8.6.md) | 0 |
