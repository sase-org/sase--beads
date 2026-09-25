# Bead: sase-18d.5 — Additive dismissed-index persistence for every writer

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.5` · **Size:** medium
**Created:** 2026-09-24 16:28:35 EDT · **Closed:** 2026-09-24 21:24:58 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

additive-dismissals: switch the cleanup transactions and every other dismissed-agents writer from full-snapshot saves to the core-wire add/remove API. Revive becomes a removal. Concurrent procs, runners, and TUIs can no longer lose each other's dismissals.

## Notes

[2026-09-25T01:24:28Z · sase-18d.5] PROPOSED FOLLOW-UP: `just check` red on the clean base tree, independent of this phase — lint (mypy) `tools/typecheck_extensionless_tools` errors in tools/sase_core_wheel_cache:433 (contextmanager arg-type) and :604 (acquired_lock needs annotation); `_lint-test-waits` flags tests/test_sase_core_wheel_cache_tool.py:490 (fixed-sleep-missing-pragma); `_lint-toobig` flags tests/tool/test_settlement.py at 1048 lines (limit 1000).

[2026-09-25T01:24:47Z · sase-18d.5] PROPOSED FOLLOW-UP: 29 scoped tests fail identically on a clean HEAD worktree (verified) — keymaps help (test_keymaps_defaults_modes, test_keymaps_display_help_agents, test_help_modal), agent prompt panel/semantic/tribe/monitor widget tests, test_agent_monitor_stop_action, test_timezone_display_tui, test_llm_provider_effort_invocation (codex), test_app_import_budget, test_no_ref_prefix_dispatch, test_visual_fixture_host_paths, test_file_panel, test_agent_group_revival_e2e::test_agents_command_palette_exposes_save_marked_group, test_agents_tab_current_project_seed.

[2026-09-25T01:24:58Z · sase-18d.5] Every dismissed-agents writer now merges through the core-wire add/remove/update API instead of full-snapshot saves. Persist-cleanup payloads (single/bulk kill, single/bulk dismiss, marked save) carry added_identities, with a legacy dismissed_identities fallback that is only ever added. Revive and loader-cleanup use removals. The runner auto-dismiss, kill_named_agent, purge, wipe and apply-path writers use add/remove/update. The generation-stamp machinery and snapshot_dismissed_agents are deleted. The artifact index syncs the set the merge left on disk. New tests: tests/test_dismissed_index_additive_writers.py (union in either order, runner-vs-TUI race, revive removes only its identities) plus thread and process concurrency tests in test_dismissed_agents_state.py. Verified: ruff, mypy src, symvision, flags, pyscripts, changelog, terminology, validate and committed-plans all pass; 264 touched/related tests pass. just check is red only on base failures (mypy tools/, test-waits, toobig, and 29 scoped tests reproduced on clean HEAD), recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-18d.1](sase-18d.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18d.4](sase-18d.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.6](sase-18d.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.5/README.md) | [sase-18d.5](sase-18d.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1ea13da`](https://github.com/sase-org/sase/commit/1ea13da1b3450d2c89da83beb47814f117e9315b) | feat(dismissed-index): persist dismissals additively for every writer | [sase-18d.5](sase-18d.5.md) | 2026-09-24 21:26:20 EDT |
