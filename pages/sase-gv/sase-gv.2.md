# Bead: sase-gv.2 — Tasks tab jump

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.2` · **Size:** small
**Created:** 2026-08-07 09:52:50 EDT · **Closed:** 2026-08-07 10:45:23 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

tasks: wire the Tasks pane task list onto the shared mixin.

## Notes

[2026-08-07T14:44:17Z · sase-gv.2] PROPOSED FOLLOW-UP: `just check`'s SASE validation gate fails on this workspace independent of any code change (init skills --check wants to overwrite 5 chezmoi sase_gate skill files); confirmed pre-existing via git stash. Investigate chezmoi skill drift for sase_gate so `just check` is green for other agents on this host.

[2026-08-07T14:45:23Z · sase-gv.2] Wired TasksPane onto PaneEntryJumpMixin: added apostrophe binding + on_key, _jump_target_count/_jump_current_index/_jump_select_index/_jump_repaint hooks, hint-decorated _create_options, and rule-5 invalidation centralized in _rebuild_list (covers all reload paths incl. the 0.25s live refresh). _hints() is now an instance method with a JUMP variant. Added 5 tests (enter/hints, hint-select+output, back-stack, escape-cancel, refresh-removes-hinted-task) - all pass. Verified: just install, just check (all lint gates green; SASE validation chezmoi-skill-drift failure is pre-existing/unrelated, confirmed via git stash), just test-scoped (1248 passed), tests/ace/tui/test_logs_pane.py (29 passed, mixin regression-free), and the config_center_tasks PNG golden refreshed/verified stable after the new ': jump' hint text.

[2026-08-07T14:46:34Z · sase-gv.2] Re-verified: PaneEntryJumpMixin wiring for Tasks pane (apostrophe jump binding, hint-decorated labels, rule-5 invalidation in _rebuild_list); just check lint gates green, just test-scoped 1248 passed, Logs pane suite unaffected, PNG golden refreshed for new hint text.

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.2/README.md) | [sase-gv.2](sase-gv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9417428`](https://github.com/sase-org/sase/commit/94174283402c3b63bfc1bf9203e708e8ff13db0a) | feat(ace): wire Tasks pane onto the shared entry-jump mixin | [sase-gv.2](sase-gv.2.md) | 2026-08-07 10:48:30 EDT |
