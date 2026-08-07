# Bead: sase-gv.1 — Shared pane entry-jump mixin and Logs migration

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.1` · **Size:** medium
**Created:** 2026-08-07 09:52:17 EDT · **Closed:** 2026-08-07 10:18:11 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

shared: add the reusable pane entry-jump mixin that owns hint allocation, the pending-prefix state machine, and the bounded back stack, then migrate the Logs pane onto it with no behavior change.

## Notes

[2026-08-07T14:17:35Z · sase-gv.1] PROPOSED FOLLOW-UP: flaky under parallel `just test-scoped` — test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit and test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_dev_update_shows_all_commit_groups failed once in a full scoped run, then passed in isolation and on a clean re-run of the same lane; unrelated to the entry-jump change

[2026-08-07T14:18:11Z · sase-gv.1] Added src/sase/ace/tui/modals/pane_entry_jump.py (PaneEntryJumpMixin + _JumpState + apply_jump_hint_prefix re-export) covering all 7 contract rules, and migrated LogsPane onto it: deleted all 5 _log_jump_* attrs, _clear_log_jump_hints, _exit_log_jump_mode, _handle_log_jump_key, _jump_to_source_index, _log_jump_hints_are_valid, and action_jump_to_entry's body; LogsPane now implements only the 4 _jump_* hooks and calls invalidate_jump_hints from _apply_load_result. _hints() strings unchanged. All 6 existing Logs jump tests pass with only attribute-name edits (jump_mode_active/jump_back_stack) and unchanged behavior assertions; added 17 mixin unit tests in tests/ace/tui/test_pane_entry_jump.py (hint width 1 vs 2, pending-prefix completion, invalid/escape exit, back-stack cap of 10, no push when index unchanged, out-of-range back-stack skip, both invalidation rules, zero-target no-op, per-instance state). just check green: every lint gate incl. symvision + scoped tests.

[2026-08-07T14:19:07Z · sase-gv.1] Extracted PaneEntryJumpMixin into src/sase/ace/tui/modals/pane_entry_jump.py and migrated LogsPane onto it; verified all 6 existing Logs jump tests pass unchanged in behavior plus 17 new mixin unit tests, and 'just check' green (all lint gates incl. symvision + scoped test lane).

## Dependencies

- **Blocks:** [sase-gv.2](sase-gv.2.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.3](sase-gv.3.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.4](sase-gv.4.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.5](sase-gv.5.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.6](sase-gv.6.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.7](sase-gv.7.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.1/README.md) | [sase-gv.1](sase-gv.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b27059f`](https://github.com/sase-org/sase/commit/b27059f51d335bb101422dae2c8274a537edab15) | refactor(ace): extract a shared pane entry-jump mixin and migrate LogsPane | [sase-gv.1](sase-gv.1.md) | 2026-08-07 10:19:57 EDT |
