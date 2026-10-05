# Bead: sase-1eq.5.1.3 — Completion, argument assist, and highlight roles

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.3` · **Size:** medium
**Created:** 2026-10-03 13:29:46 EDT · **Closed:** 2026-10-04 01:39:24 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

## Description

tui-completion: move completion, argument-assist, and syntax modules to macro names. Rename in-process highlight roles to macro.* in the TUI and the CLI render mirror together.

## Notes

[2026-10-04T04:59:26Z · sase-1eq.5.1.3--3] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version failed as NEW under the same ToolRun with textual.css.query.NoMatches on #frontmatter-raw (FrontmatterPanel hidden) during AceApp.run_test mount. Isolation rerun passed. first_seen before this phase, distinct_agents=12, touched:false. Different node than closed sase-pe (test_enter_loads_raw_definition_and_binds_source). sase-ct is the retired umbrella that forbids +1. Land agent should file a node-specific flake task; class epic sase-j7.

[2026-10-04T04:59:29Z · sase-1eq.5.1.3--3] PROPOSED FOLLOW-UP: tests/ace/tui/test_launch_context_source.py::test_every_tick_rebroadcasts_to_mounted_views failed as NEW under just check ToolRun e9e1f8b215487a1bf3a3463dffd472ca (4-worker scoped lane) with AssertionError on LaunchContextState identity after a tick rebroadcast; touched:false, not in this phase diff. Exact node already tracked by sase-1fn. Isolation rerun on this tree passed in 10.38s with the title test. Close this phase anyway; land agent can +1 sase-1fn.

[2026-10-04T05:39:04Z · sase-1eq.5.1.3--4] PROPOSED FOLLOW-UP: tests/ace/tui/test_artifacts_limit_keys.py::test_agents_tab_ctrl_j_does_not_rewrite_artifacts_query failed as NEW under just check ToolRun 40271538fb51cb3ea8f9569e3d0a466b with textual.css.query.NoMatches on #frontmatter-raw (FrontmatterPanel hidden) during AceApp.run_test. Isolation rerun passed (2 passed in 9.79s with test_on_mount_refines_title). first_seen before this phase, distinct_agents=4, touched:false, file not in this phase diff. Same #frontmatter-raw class as note #1; different node than closed sase-pe. sase-ct is the retired umbrella that forbids +1. Land agent should file a node-specific flake task; class epic sase-j7.

[2026-10-04T05:39:24Z · sase-1eq.5.1.3--4] git-mv of completion/arg-assist/syntax modules to macro names; highlight roles xprompt.*→macro.* in TUI+CLI mirror; MacroArgumentSource durable reader maps "xprompt"→"macro" while core still emits "xprompt"; remaining xprompt helper names (_get_xprompt_arg_completion_context, _try_auto_xprompt_arg_completion, _completion_kind="xprompt", JinjaScopeKind "xprompt") left for later phases; show_macro_arg_hint + arg-panel copy; targeted goldens inspected (arg-completion + highlight run clean, 13 unchanged, PNG filenames unchanged). just check ToolRun 40271538fb51cb3ea8f9569e3d0a466b: 1 NEW #frontmatter-raw flake on test_agents_tab_ctrl_j (isolation passed, same class as note #1, recorded as PROPOSED FOLLOW-UP) plus 5 KNOWN (symvision KillProvenance). Epic-symbols none. Closed anyway per phase policy.

## Dependencies

- **Depends on:** [sase-1eq.5.1.2](sase-1eq.5.1.2.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.5.1.4](sase-1eq.5.1.4.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.3.md) | [sase-1eq.5.1.3](sase-1eq.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7408ed`](https://github.com/sase-org/sase/commit/e7408ed219af298cefa55af04496d778d2d05f8e) | feat(ace): rename completion and highlight roles to macro | [sase-1eq.5.1.3](sase-1eq.5.1.3.md) | 2026-10-04 02:52:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.3--4][1] | Need phase scope, design, notes, and current status before closing | 1 |
| read-by | [agent:sase-1eq.5.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->
