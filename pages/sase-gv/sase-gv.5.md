# Bead: sase-gv.5 — Updates tab jump for Plugins and Agent CLIs

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.5` · **Size:** medium
**Created:** 2026-08-07 09:53:13 EDT · **Closed:** 2026-08-07 11:21:00 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

updates: wire the Updates pane's active-sub-tab option list onto the shared mixin, skipping group headers and no-opping on the list-free Core sub-tab.

## Notes

[2026-08-07T15:20:16Z · sase-gv.5] PROPOSED FOLLOW-UP: `just validate` fails on pre-existing sase_gate skill drift — the 5 deployed provider SKILL.md copies are stale relative to the source changed in 7ca857a9a, so `just check` aborts before its test lane on any workspace.

[2026-08-07T15:20:33Z · sase-gv.5] PROPOSED FOLLOW-UP: LogsPane still swallows g/G during jump mode — LogSourceList._handle_detail_scroll_key stops those keys before the pane sees them, so hints 16 (g) and 42 (G) are unreachable; PluginsBrowserList now defers to jump mode and Logs should do the same.

[2026-08-07T15:21:00Z · sase-gv.5] Wired the Updates pane onto PaneEntryJumpMixin via a new PluginsBrowserJumpMixin: active-sub-tab dispatch through _active_option_list, item rows only (_is_item skips __header__ rows), Core reports 0 targets and jump_to_entry is in check_action's browse_only set. Hints decorate plugin rows in _create_options and agent-CLI rows in _render_agent_clis/_repaint_agent_cli_options; selection moves by assigning highlighted like action_next_option. Jump state resets on sub-tab switch, filter change, and catalog reload. PluginsBrowserList now defers g/G to jump mode so those hints are reachable. Hint lines gained "' jump" plus JUMP variants (wording trimmed so the 108-col lines still show [ / ] sub-tab; _core_hints untouched). Verified: 8 new tests in tests/ace/tui/test_plugins_browser_pane_jump.py, 270 plugins/config-center/admin-center tests, just lint (ruff+mypy+symvision+toobig) clean, just test-scoped 2383 passed, full just test-visual 414 passed with config_center_plugins/agent_clis goldens refreshed. just check itself aborts earlier on unrelated sase_gate skill drift (noted as a follow-up).

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.5/README.md) | [sase-gv.5](sase-gv.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d7f34d8`](https://github.com/sase-org/sase/commit/d7f34d84dc9dd98447b57a499ea24fa02dcc2108) | feat(ace): add entry-jump mode to the Updates tab's Plugins and Agent CLIs panes | [sase-gv.5](sase-gv.5.md) | 2026-08-07 11:23:50 EDT |
