# Bead: sase-18f.4 — Repair ACE TUI tests that fail on clean master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.4` · **Size:** medium
**Created:** 2026-09-24 17:18:57 EDT · **Closed:** 2026-09-24 21:52:17 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

tests-ace-ui: fix the ACE/TUI failures from the legacy-agents-UI removal and the deck cutover. This includes the prompt-panel monitor tests (sase-184), the completion-accept key move to ctrl-f, the command-line visual fixture host path, the TUI import budget, and the artifacts ref-prefix contract. Fix the code or update the tests of intentionally removed behavior.

## Notes

[2026-09-25T01:51:08Z · sase-18f.4] PROPOSED FOLLOW-UP: mypy red on clean master in tools/sase_core_wheel_cache:433 (contextmanager arg-type on _identity_lock) and :604 (acquired_lock needs annotation) — from adebe400d (sase-18f.8); `.venv/bin/python tools/typecheck_extensionless_tools --mypy .venv/bin/mypy` fails on a stashed clean tree, so `just check` stops at lint (mypy).

[2026-09-25T01:51:22Z · sase-18f.4] PROPOSED FOLLOW-UP: test-waits lint red on clean master — tests/test_sase_core_wheel_cache_tool.py:490 fixed-sleep-missing-pragma (from the sase-18f.8 lsp-build-cache tests); needs a `# sase-test-wait: <reason>` pragma or an observable wait.

[2026-09-25T01:51:34Z · sase-18f.4] PROPOSED FOLLOW-UP: symvision + toobig red on clean master from concurrent landings — unused public AgentSurvivorsError/Survivor (src/sase/ace/tui/actions/agents/_kill_termination.py) and environ_has_launch_key (src/sase/agent/process_tree.py); stale --epic-symbol sase-18i.2(...) Justfile entries now that bead sase-18i.2 is closed; tests/tool/test_settlement.py is 1048 lines (limit 1000).

[2026-09-25T01:51:45Z · sase-18f.4] PROPOSED FOLLOW-UP: tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed fails deterministically on clean master — sase-18d.1 (e3f3a4bd4) added src/sase/ace/dismissed_agents_state.py add_dismissed_agents/remove_dismissed_agents, whose load-modify-save fallback calls save_dismissed_agents; they need review in _REVIEWED_DISMISSED_SAVE_CONTEXTS. Deliberately not exempted here: the audit only detects save_dismissed_agents calls, so future callers of the new APIs (sase-18d) are not audited — decide whether to extend the audit.

[2026-09-25T01:51:58Z · sase-18f.4] PROPOSED FOLLOW-UP: load-sensitive/environmental, not repaired — tests/test_agent_load_tiering_production_oracle.py::test_production_machine_query_oracle_repairs_owner_after_index failed in the broad scoped run but passed alone (flake candidate); tests/ace/tui/terminal_smoke/test_ace_terminal_smoke.py::test_sase_screenshot_cli_captures_png_with_tmux (slow lane only) fails with tmux "File name too long" because the agent tmp path makes the socket path exceed the unix limit.

[2026-09-25T01:52:17Z · sase-18f.4] Repaired all 20 deterministic ACE/TUI clean-master failures (tests/ace sweep: 21 failed -> 14364 passed on rerun, non-visual/non-slow). Code fix: ref: pane-prefix dispatch moved into artifact_tabs.is_unconfigured_ref_pane (artifacts ref-prefix contract). Test updates for intentionally removed/changed behavior: prompt-panel monitor/steps/xprompts/semantic tests flatten card documents (sase-184), tribe-prompts warms a fake tag catalog, completion Ctrl+E->Ctrl+F titles, ctrl-e end-of-line test stays in the completing token, LLM Calls fold routing stub + expectations, AgentInfoPanel view_mode kwarg, deck search overlay jump-panel test, help column-balance bound, TUI import budget 3290->3400 (closure grew 3246->3355 from features + toobig splits; deferred-module probe kept), /home/test allowed as synthetic visual-fixture owner. Also fixed the broader scoped-lane fallout: deleted zoom-modal file-cap test (covered by deck file_line_status), palette e2e uses semicolon, monitor-stop tests target the planner-kill route + stop-only fallback, keymap help labels, timezone fake agent identity, codex -c effort assertion. ruff, fmt, fmt-md, mypy (4964 files) green; no --epic-symbol leftovers. Remaining red on clean master (mypy tools/, test-waits, symvision, toobig, dismissed-save audit) recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-18f.1](sase-18f.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.2](sase-18f.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.4/README.md) | [sase-18f.4](sase-18f.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bf3aa6c`](https://github.com/sase-org/sase/commit/bf3aa6c8a39da17fa12c29ef582194a117d9cb83) | fix(sase-18f.4): repair ACE TUI tests that fail on clean master | [sase-18f.4](sase-18f.4.md) | 2026-09-24 21:53:35 EDT |
