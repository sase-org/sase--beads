# Bead: sase-17p.5 — Settle hand-off runs truthfully after crashes and deliver once

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.5` · **Size:** large
**Created:** 2026-09-24 08:40:24 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

settlement: feed owner facts into reconcile, record stop and timeout causes from the owner's termination intent, settle from proc and monitor settlement, publish exactly one notification for proc-owned hand-offs, and report expired owner logs explicitly.

## Notes

[2026-09-24T17:24:50Z · 0qz--code] symvision_green_master sweep: MonitorToolHandoff->_MonitorToolHandoff, parse_monitor_tool_words->_parse_monitor_tool_words, envelope_from_resolved->_envelope_from_resolved, read_output_tail->_read_output_tail. No epic-symbol; update imports if you touch these.

[2026-09-24T17:57:10Z · sase-17p.5] PROPOSED FOLLOW-UP: close sase-145 — persisted ToolRun finish diagnostics (spawn failure, stage-ingest, log-write facts) already render in 'sase tool show RUN -j' (run.diagnostics) and the human DIAG block; tests/tool/test_settlement.py::test_persisted_diagnostics_render_in_show_json_and_human proves both renderings, and tests/tool/test_executor.py::test_finish_diagnostics_persist_spawn_and_truncation proves the core persistence. Left open per this worker's close-only-17p.5 rule.

[2026-09-24T17:57:29Z · sase-17p.5] PROPOSED FOLLOW-UP: TUI action for the tool-run settlement notification — deliver_handoff_settlement publishes sender=tool-run with action=None and action_data {run_id, command: 'sase tool show RUN'} because no generic 'run command' notification action exists and an unknown action string makes the TUI warn. A real action that opens/prints the run is E5 scope.

[2026-09-24T17:57:39Z · sase-17p.5] PROPOSED FOLLOW-UP: pre-existing gate failures seen while verifying (all reproduce on a clean tree with this phase stashed; none touch this phase's files): (1) just check stops at 'lint (feature flags)': rule 6 'tool_handoff' names missing bead sase-17v, rule 7 closed flag bead sase-17k still has a surviving agent_decks definition; (2) tests/tool/test_handoff.py:205 fixed-sleep-missing-pragma fails the test-waits lint; (3) toobig: src/sase/ace/tui/widgets/decks/panel.py has 1051 lines; (4) symvision stops at 'Private functions/classes should not be imported' for ~70 unrelated private symbols in llm_provider/usage, plan_chain, ace modals; (5) 24 scoped-lane tests fail identically on the clean tree (ace tui prompt-panel widgets, completion snapshot/kind coverage, tests/main/test_parser_tool.py::test_tool_help_advertises_implemented_verbs, core-facade cleanup, fakey CLI help, import budget). The remaining check gates (ruff, mypy, format, changelog, pyscripts, validate, committed plans) pass and were run individually.

## Dependencies

- **Depends on:** [sase-17p.3](sase-17p.3.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17p.4](sase-17p.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.6](sase-17p.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17p.5.md) | [sase-17p.5](sase-17p.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7173669`](https://github.com/sase-org/sase/commit/71736697dcb97b14cceb96cf687dfa24d6454d17) | feat(tool): settle hand-off ToolRuns from owner facts and deliver once (sase-17p.5) | [sase-17p.5](sase-17p.5.md) | 2026-09-24 14:00:16 EDT |
