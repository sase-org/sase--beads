# Bead: sase-1v7.3 — TUI surfaces for on-demand rosters and roster reads

[Bead Pages](../README.md) / [sase-1v7](README.md) / sase-1v7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1g7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1g7.md) · **Assignee:** `sase-1v7.3` · **Size:** small
**Created:** 2026-11-25 15:44:41 EST · **Closed:** 2026-11-25 19:00:40 EST
**Plan:** [202611/on\_demand\_web\_rosters.md](https://github.com/sase-org/sase--plans/blob/main/202611/on_demand_web_rosters.md)

## Description

tui-surfaces: show roster reads correctly in the agent MEMORY lane, including the report hint and the version chip. Give the Memory panel's on-demand webs an ON DEMAND badge, a `Roster` row, a `Read when` row, a `Last roster read` row, and a rail-row suffix. Update targeted visual goldens if they cover these surfaces.

## Notes

[2026-11-25T23:09:49Z · sase-1v7.3] PROPOSED FOLLOW-UP: Regenerate the checked-in CLI completion snapshot — the two tests in tests/completion/test_snapshot.py fail because the argparse tree differs from the snapshot, and the targeted test run reproduces the drift.

[2026-11-26T00:00:28Z · sase-1v7.3--1] PROPOSED FOLLOW-UP: Update the committed design-decision reference for the new rosters-load-on-demand decision — test_real_decisions_web_renders_every_record reproducibly fails because webs-render-in-their-own-section supersedes decisions:rosters-load-on-demand, but that anchor is absent from docs/reference/design-decisions.md; this is outside the TUI phase.

[2026-11-26T00:00:40Z · sase-1v7.3--1] Verified Memory panel on-demand badge, roster/read-trigger/last-read rows and rail suffix, plus MEMORY-lane roster report hint and descriptor-version chip; focused TUI and roster-loading tests passed (84 passed). The monitored sase tool run check ended exit 1 with no_new_failures: two known completion snapshot drift failures already recorded as a proposed follow-up, and the known decisions-web reference test failure was reproduced and recorded as a proposed follow-up. Epic-symbol audit was clear.

## Dependencies

- **Depends on:** [sase-1v7.1](sase-1v7.1.md) ✓ · ⧖ 2026-11-25
- **Depends on:** [sase-1v7.2](sase-1v7.2.md) ✓ · ⧖ 2026-11-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1v7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1v7.3.md) | [sase-1v7.3](sase-1v7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8e6818d`](https://github.com/sase-org/sase/commit/8e6818d0a6bc0f6eb1b3fd8071385b152af04752) | feat(tui): show on-demand memory rosters | [sase-1v7.3](sase-1v7.3.md) | 2026-11-25 18:12:13 EST |
