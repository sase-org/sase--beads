# Bead: sase-1jm.3.1.8.3 — Live-key toasts, read isolation, marks, footer, help, and info row

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.3` · **Size:** medium
**Created:** 2026-10-11 19:18:52 EDT · **Closed:** 2026-10-11 22:37:48 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

action-boundary-fixes: make live-only keys reach their Archive guards so they toast instead of being silently swallowed. Stop copy readers from falling back to the parked Inbox agent, and guard or route the remaining unaudited Inbox actions. Render Archive marks and refresh the footer after mark and cursor changes. Remove the nonfunctional Enter read hint, fix the overflowing help row, and gate help and leader chrome on the beta. Fix the info row's color, key label, and resize alignment (the cause of the flaky missing-index golden), and the exception chip drop order.

## Notes

[2026-10-12T02:37:31Z · sase-1jm.3.1.8.3] Action audit: live-only keys dispatch to Archive guard toasts while command palette entries stay hidden; edit_hooks, edit_spec, open_tmux, and start_tmux_mode are guarded. Metadata, patch, and artifact readers use only the active typed Archive selection and do not fall back to parked Inbox rows. Archive marks repaint with the cursor/footer; help and leader controls are beta-gated, Enter read hints are removed, the info row uses configured toggle/chrome and resizes, exception chips survive model/runtime trimming, and same-choice grouping is a no-op. Consolidated 13-file focused suite and all 10 targeted Archive/help visual cases passed; 8 Archive PNGs refreshed.

[2026-10-12T02:37:39Z · sase-1jm.3.1.8.3] PROPOSED FOLLOW-UP: Triage five guarded-check failures reproduced identically on clean HEAD: TUI import budget (tracked by sase-13p) and agent display meta priority (tracked by sase-1k4), plus workflow Project metadata, project-current help choices, and project/suggest owner completion-kind coverage; do not block this phase.

[2026-10-12T02:37:48Z · sase-1jm.3.1.8.3] Action-boundary fixes implemented; focused 13-file suite and 10 targeted Archive/help visual cases passed, with 8 Archive PNGs refreshed. The five remaining guarded-check failures were reproduced identically on clean HEAD and recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.3/README.md) | [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8270bf7`](https://github.com/sase-org/sase/commit/8270bf768fed558909db3ef5371bca298cecd42f) | fix(tui): keep Archive actions read-only | [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) | 2026-10-11 22:38:57 EDT |
