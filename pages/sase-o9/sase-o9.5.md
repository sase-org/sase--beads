# Bead: sase-o9.5 — Documentation and visual snapshot suite

[Bead Pages](../README.md) / [sase-o9](README.md) / sase-o9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md) · **Assignee:** `sase-o9.5` · **Size:** small
**Created:** 2026-08-17 06:54:28 EDT · **Closed:** 2026-08-17 08:58:36 EDT
**Plan:** [202608/procs\_tab\_monitor\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)

## Description

docs-and-visual-suite: rewrite the Procs Tab documentation for monitor rows, counts, and the jump key, then rebaseline and extend the Procs PNG goldens.

## Notes

[2026-08-17T12:57:41Z · sase-o9.5] PROPOSED FOLLOW-UP: Justfile _lint-symvision still carries --epic-symbol sase-o8.4(PlaceholderRankingMetadata) after that phase closed, so just check / just check-full fail for every agent until the stale entry is removed and the symbol is wired, privatized, or pragma’d — reproduced 2026-08-17 on this tree; same leftover class as parent DISCOVERED ISSUE / ready task sase-o7 (Justfile now names o8.4, not o9.2).

[2026-08-17T12:57:58Z · sase-o9.5] PROPOSED FOLLOW-UP: Other Admin Center tab-number docs are still drifted — docs/ace.md Projects says press 3 (tab is 4) and Statistics says press 4 (tab is 5); docs/telemetry.md also says Statistics is 4. This phase only corrected the Procs Tab section (3, not 5).

[2026-08-17T12:58:13Z · sase-o9.5] PROPOSED FOLLOW-UP: Procs hints clip at ~90 columns when ⏎: agent is shown — scroll/Tab/Esc tokens fall off; at 120 the line still reaches Esc: but is tight. Captured in config_center_procs_tab_monitors_90x40.png; not a new regression vs the pre-epic 120-col Esc: edge clip.

[2026-08-17T12:58:36Z · sase-o9.5] Rewrote docs/ace.md Procs Tab: Monitors subsection (orange gear, agent name, live_reply.md stream, Enter jump, both scopes, K stop path), header counts (blue=plain/orange=monitor, scoped, dim zero chips), Enter keybinding; corrected open key 3 (not 5) and 0.25s tick. Extended visual fixtures with running just check-full + finished pytest -x monitor rows; rebaselined config_center_procs_tab_120x40.png after inspecting actual/diff; added monitor-focused goldens at 120x40 and 90x40 (header chips, marked rows, streamed tail, ⏎: agent). Home resume procs goldens unchanged. just test-visual procs+home: 7 passed. just test-scoped: 452 passed. just check lint gates through ruff/mypy passed; full just check blocked by unrelated stale --epic-symbol sase-o8.4 (PROPOSED FOLLOW-UP).

[2026-08-17T13:00:32Z · sase-o9.5] Docs and PNG goldens for Procs monitors: ace.md documents monitor rows/header chips/Enter; visual fixtures add running+finished monitors; rebaselined procs tab 120x40 and added 120x40+90x40 monitor-focused snapshots. just test-visual Procs+home: 7 passed; just test-scoped: 452 passed.

## Dependencies

- **Depends on:** [sase-o9.3](sase-o9.3.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-o9.4](sase-o9.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o9.5/README.md) | [sase-o9.5](sase-o9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`26fefda`](https://github.com/sase-org/sase/commit/26fefdab753e6a0bfbed1dcb2aacec935e3d12da) | docs(ace): document Procs monitors and add visual goldens | [sase-o9.5](sase-o9.5.md) | 2026-08-17 09:01:30 EDT |
