# Bead: sase-gv.6 — Config tab jump over visible tree rows

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.6` · **Size:** medium
**Created:** 2026-08-07 09:53:18 EDT · **Closed:** 2026-08-07 11:08:45 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

config: wire the config field tree onto the shared mixin by decorating node labels in place, without rebuilding the tree or disturbing fold state.

## Notes

[2026-08-07T14:50:05Z · sase-gv.6] PROPOSED FOLLOW-UP: `just check` SASE validation fails on `init skills --check` — the 5 provider copies of sase_gate/SKILL.md in chezmoi are stale versus src/sase/xprompts/skills/sase_gate.md since commit 7ca857a9a; needs a `sase init skills` run. Pre-existing on master, unrelated to sase-gv.

[2026-08-07T15:08:03Z · sase-gv.6] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent failed once under the loaded full-suite run (2026-08-07) and passes in isolation — timing-sensitive flake, unrelated to this phase.

[2026-08-07T15:08:45Z · sase-gv.6] Wired ConfigPane onto PaneEntryJumpMixin: apostrophe binding + on_key with jump-mode first refusal (skipped while the filter/path input has focus); jump targets are the visible tree rows from _visible_tree_nodes in render order (collapsed children excluded); hints are painted by node.set_label() in place via apply_jump_hint_prefix, never through _rebuild_tree, so fold state survives; _jump_select_index goes through _move_cursor so the detail panel and bookmark update; rule-5 invalidation applied at the single _rebuild_tree choke point (filter, m, r, and : path jump all funnel there). Hint line reworked to fit the 108-col pane at 120x40 (was 138 chars, clipped; now 108) and distinguishes ': hint from :: path. Verified: 8 new tests in tests/ace/tui/test_config_pane_widget_jump.py (hint order, hint jump + detail repaint, ' ' back stack, Esc cancel, collapsed sections preserved, filter rebuild clears hints, filter-focus no-op, hint-line variants) plus the updated navigation test; 5 config_center_config PNG goldens refreshed and re-verified green (xprompts golden unaffected); all lint gates green under just check; the escalated full test lane ran 26870 passed with one unrelated timing flake (test_stall_watchdog, passes in isolation) and the pre-existing init-skills validation failure — both recorded as PROPOSED FOLLOW-UP notes.

[2026-08-07T15:09:52Z · sase-gv.6] Config tab jump mode implemented over visible tree rows via PaneEntryJumpMixin; 8 new tests + navigation test update pass; PNG goldens refreshed; lint gates green; full suite 26870 passed.

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.6/README.md) | [sase-gv.6](sase-gv.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02758f8`](https://github.com/sase-org/sase/commit/02758f8f18f629b85f112c0277b4f7b0cb748321) | feat(ace): add hint-jump mode to the Config Center field tree | [sase-gv.6](sase-gv.6.md) | 2026-08-07 11:11:29 EDT |
