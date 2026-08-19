# Bead: sase-r0.7 — Launch Control \`t\` and the tmux Agent panel

[Bead Pages](../README.md) / [sase-r0](README.md) / sase-r0.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07y.md) · **Assignee:** `sase-r0.7` · **Size:** medium
**Created:** 2026-08-19 11:57:05 EDT · **Closed:** 2026-08-19 15:13:49 EDT
**Plan:** [202608/tmux\_agent\_launcher.md](https://github.com/sase-org/sase--plans/blob/main/202608/tmux_agent_launcher.md)

## Description

ace: bind `t` in Launch Control and add the tmux Agent modal, its styles, footer/help wiring, and behavior tests.

## Notes

[2026-08-19T19:13:16Z · sase-r0.7] PROPOSED FOLLOW-UP: Justfile lint (symvision) is broken repo-wide right now — src/Justfile:343-345 still pass --epic-symbol "sase-r1.4(UpdateOptionChip)", --epic-symbol "sase-r1.4(UpdateOptionRow)", --epic-symbol "sase-r1.4(UpdatePanelState)" for src/sase/ace/tui/update_panel_state.py, but bead sase-r1.4 is now closed, so symvision refuses these exemptions and `just lint`/`just check` fail for every agent (unrelated to sase-r0). Either resolve the underlying unused symbols in update_panel_state.py or re-key those three Justfile lines to a still-open bead.

[2026-08-19T19:13:49Z · sase-r0.7] Added the tmux Agent Launch Control surface: TmuxAgentModal (src/sase/ace/tui/modals/tmux_agent_modal.py) — worker-loaded catalog, key/enter launch, s=safe launch (strips bypass args), routing-disabled/not-installed row states, exact-command description strip, q closes only when unclaimed by a provider — plus ModelsPanelTmuxAgentMixin wiring the 't' binding into ModelsPanel (warns when not inside tmux), footer text, __init__ registration, and #tmux-agent-* styles.tcss geometry mirroring #provider-routing-*. Verified: whole-repo 'just fmt'+'ruff check'+'mypy' clean (3536 files); new tests/ace/tui/test_tmux_agent_modal.py (11 tests: row rendering, description strip, not-installed navigation skip, enter/selector-key/safe launch, launch-failure toast, worker cancellation on unmount, panel 't' wiring + not-in-tmux warning) all pass; tests/test_models_panel_keymaps.py and tests/test_models_panel_runner_limit.py updated and passing; full tests/test_models_panel*.py + tests/ace/tui/modals/test_agent_workspace_tmux_modal.py suite (351 tests) passes with no regressions. Full-repo 'just check'/'just lint' currently fails on an unrelated, pre-existing symvision staleness bug from closed bead sase-r1.4 (see PROPOSED FOLLOW-UP note) and 'just test-scoped' escalates to the full 34k-test suite because this ephemeral workspace's coverage baseline is 1175 commits stale — neither is caused by this phase's diff; confirmed via 'sase bead epic-symbols sase-r0.7' that this phase itself has no --epic-symbol entries to resolve.

[2026-08-19T19:14:46Z · sase-r0.7] Re-verifying publish status per finalizer instructions.

## Dependencies

- **Depends on:** [sase-r0.4](sase-r0.4.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r0.8](sase-r0.8.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r0.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r0.7/README.md) | [sase-r0.7](sase-r0.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9ece10`](https://github.com/sase-org/sase/commit/b9ece108998721586586628436778d0ddf3d3574) | feat(ace): add Launch Control tmux Agent panel bound to \`t\` | [sase-r0.7](sase-r0.7.md) | 2026-08-19 15:15:37 EDT |
