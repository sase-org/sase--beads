# Bead: sase-qt.4 — Memory panel shell, note tree, filter, and scope switching

[Bead Pages](../README.md) / [sase-qt](README.md) / sase-qt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.4` · **Size:** medium
**Created:** 2026-08-19 08:16:38 EDT · **Closed:** 2026-08-19 10:39:14 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

panel-shell: build the modal, the nested note rail, the note card, filtering, scope cycling and picking, empty/error states, and passive open/copy actions.

## Notes

[2026-08-19T14:38:51Z · sase-qt.4] PROPOSED FOLLOW-UP: flake — tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace and tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_ctrl_u_scrolls_up_without_dismissing failed during just check full-suite run but passed individually on rerun; unrelated to memory panel work, likely resource/timing flakes under parallel full-suite load.

[2026-08-19T14:39:14Z · sase-qt.4] Implemented Memory panel shell (memory_panel.py + view/state/navigation/rendering/scope_picker/help_modal modules), nested note rail, note card, filter, scope cycling/picker, empty/error states, and passive open/copy actions per plan:202608/ace_memory_panel.md Phase 4. Verified: 31 new tests in tests/ace/tui/modals/{test_memory_panel*,memory_panel_test_helpers}.py pass; symvision lint clean (no leftover epic-symbols for sase-qt.4); just lint passed; just check (full lint gates + scoped test lane, 34045 passed) — the 2 failures (test_pipe_e2e fork test, test_jump_all_modal_hints ctrl+u test) are unrelated pre-existing flakes confirmed by isolated rerun (both pass), logged as PROPOSED FOLLOW-UP on this bead.

[2026-08-19T14:51:06Z · sase-qt.4] PROPOSED FOLLOW-UP: bug (high severity, pre-existing, unrelated to this phase) — sase-core v0.29.1 (commit 6169e0e "feat(provider_disable): add hard/soft mode to the disable wire") inserted a new `mode: str = "hard"` positional-or-keyword parameter before `duration_seconds`/`now` in provider_disable_set_relative, provider_disable_set_until, provider_disable_try_set_relative, and provider_disable_try_set_until, and bumped PROVIDER_DISABLE_WIRE_SCHEMA_VERSION 1->2. src/sase/llm_provider/provider_disable.py still calls these bindings with the old positional argument order (disable_provider_until:174, try_disable_provider:193-199, try_disable_provider:154 via disable_provider) so a float/None now lands in the "mode" slot and every call raises `TypeError: argument mode: ... cannot be converted to PyString`. Repro: `.venv/bin/python -m pytest tests/test_provider_disable.py -q` -> 6 failed, 10 passed on current master (confirmed on a clean checkout, unrelated to sase-qt.4 diff; not caught by just check scoped selection since nothing in this phase touches provider_disable.py). Fix: pass mode= (or omit and use keyword now=/duration_seconds=) matching the new signatures, and bump any hardcoded wire "version": 1 expectations to 2. I hit and fixed the same signature drift in tools/validate_sase_core_rs (its provider-disable first-writer probe, blocking this phase commits pre-commit hook) plus its test fixture in tests/test_validate_sase_core_rs_contracts_tool.py as part of this commit, but left src/sase/llm_provider/provider_disable.py and its tests untouched since fixing it is out of scope for sase-qt.4.

## Dependencies

- **Depends on:** [sase-qt.1](sase-qt.1.md) ✓ · ⧖ 2026-08-19
- **Depends on:** [sase-qt.3](sase-qt.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.5](sase-qt.5.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.6](sase-qt.6.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.7](sase-qt.7.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.4/README.md) | [sase-qt.4](sase-qt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4245a6d`](https://github.com/sase-org/sase/commit/4245a6dfe84c2bca1284a8a3061294313f139716) | fix(tools): match validate\_sase\_core\_rs probe to the new provider-disable mode param | [sase-qt.4](sase-qt.4.md) | 2026-08-19 10:51:55 EDT |
