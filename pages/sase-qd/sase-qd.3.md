# Bead: sase-qd.3 — Make every Projects-tab key configurable

[Bead Pages](../README.md) / [sase-qd](README.md) / sase-qd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.3` · **Size:** medium
**Created:** 2026-08-18 18:14:40 EDT · **Closed:** 2026-08-18 19:38:53 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

keymap-scope: add the `ace.keymaps.projects` scope covering all three Projects-tab sub-tabs, following the statistics/glossary pattern (dataclass, defaults, schema, loader, binding builder, registry field, pane wiring), and render the hints line from the configured keys instead of hardcoded letters.

## Notes

[2026-08-18T23:37:54Z · sase-qd.3] PROPOSED FOLLOW-UP: tests/_suite_gate.py has grown to 1197 lines, over the toobig lint limit of 1000 — `just check`/`just check-full` fail on lint (toobig) for every agent regardless of their diff. File a task to split or trim tests/_suite_gate.py back under the limit.

[2026-08-18T23:38:23Z · sase-qd.3] PROPOSED FOLLOW-UP: tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces is flaky (~1/8 runs) on master, unrelated to this phase. Root cause: ProjectsPane._apply_current_project_display() (added in sase-qd.2) calls _refresh_options() unconditionally whenever the current-project resolve worker completes, and that refresh reads the stale _session_state.projects bookmark identity if it races ahead of the async on_option_list_option_highlighted message that would have updated the bookmark to a just-set OptionList.highlighted index — resetting the highlighted row and any project_filter derived from it. Reproduced by rerunning the test 5-8x on a clean master checkout.

[2026-08-18T23:38:53Z · sase-qd.3] Added the ace.keymaps.projects scope (dataclass fields, schema, default_config.yml, registry loader, build_projects_bindings/build_projects_inventory_bindings) covering all three Projects-tab sub-tabs (projects/repos/workspaces), following the statistics/glossary pattern; hints lines now render from configured keys via key_display_name instead of hardcoded letters. Verified: ruff+mypy clean on all touched files; targeted suite (tests/ace/tui/test_projects_pane.py, tests/test_keymaps_defaults.py, tests/test_keymaps_validation.py, tests/ace/tui/modals/ -k 'project or keymap') is 186 passed; test_default_config_matches_public_schema passed confirming default_config.yml/sase.schema.json stay in sync. just check's lint gates all pass except a pre-existing, unrelated lint(toobig) violation on tests/_suite_gate.py (not in this diff, already over the 1000-line limit on master) -- recorded as a PROPOSED FOLLOW-UP note. Also identified and recorded a pre-existing flaky race (~1/8 runs, reproduces on master too) in test_cross_navigation_and_escape_surface_disabled_workspaces caused by sase-qd.2's current-project resolve worker racing the OptionList highlighted-bookmark update; not caused by this phase's diff.

## Dependencies

- **Depends on:** [sase-qd.2](sase-qd.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qd.4](sase-qd.4.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.3/README.md) | [sase-qd.3](sase-qd.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3df6abe`](https://github.com/sase-org/sase/commit/3df6abe123b9497d095a2cbb966fd0b525e65311) | feat(tui): make every Projects-tab key configurable | [sase-qd.3](sase-qd.3.md) | 2026-08-18 19:39:46 EDT |
