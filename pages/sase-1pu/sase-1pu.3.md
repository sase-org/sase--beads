# Bead: sase-1pu.3 — Select agent-artifact marker audits for marker-writer changes (sase-1mv)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.3` · **Size:** medium
**Created:** 2026-10-29 19:19:01 EDT · **Closed:** 2026-10-29 19:55:08 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

marker-audit-selection: make scoped test selection include both AST audit modules when a changed source file writes a tracked agent-artifact marker, without exceeding the contract-set serial budget or weakening the audits. Add selector regression tests and show that a marker-writer change selects both audits.

## Notes

[2026-10-29T23:35:33Z · sase-1pu.3] PROPOSED FOLLOW-UP: tests/contract_manifest.txt lists tests/test_core_finalizer_handoff.py but the file carries no pytest.mark.contract marker, so test_contract_manifest_matches_marker_selection fails on the clean base tree too (verified via git stash); re-mark the file or refresh the manifest

[2026-10-29T23:54:59Z · sase-1pu.3] TASK RESOLVED: sase-1mv — scoped selection now adds both marker AST audits (mutation + path-passing) with rule marker-audit whenever a changed src/ .py file contains a tracked marker literal (RULE_MARKER_AUDIT in tests/_test_selection_rules.py, wired into select_tests; literal catalog imported from the audit helpers so the trigger cannot drift). Evidence: 4 new regression tests in tests/test_test_selection_marker_audits.py pass (positive fails with the select_tests wiring stashed); real-tree repro selects both audits for src/sase/axe/run_agent_exec_markers.py and run_agent_runner_finalize.py and stays silent for literal-free src/sase/file_references.py; contract manifest untouched (90 entries); audits unchanged; ruff/mypy/symvision + full selection-engine blast radius green; wrapped check run 30fc9c7c53687497aeb55e6d6a19ef7e passed all lint gates, test lane handed to monitor. Known pre-existing failure test_contract_manifest_matches_marker_selection (missing contract marker on test_core_finalizer_handoff.py) reproduces on the clean base tree; recorded as PROPOSED FOLLOW-UP.

[2026-10-29T23:55:08Z · sase-1pu.3] marker-audit rule selects both AST audits for marker-writer changes; 4 regression tests pass (positive verified to fail without the wiring); contract manifest and audits untouched; lint gates + selection blast radius green; one pre-existing clean-base contract-manifest failure recorded as PROPOSED FOLLOW-UP

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.3.md) | [sase-1pu.3](sase-1pu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fd8882c`](https://github.com/sase-org/sase/commit/fd8882c6af267424c4f3e1e131634264a2b59b74) | feat(scope): select marker audits for marker-writer changes | [sase-1pu.3](sase-1pu.3.md) | 2026-10-29 20:39:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.1][1] | Cite sibling follow-up for stale contract_manifest flake | 1 |
| read-by | [agent:sase-1pu.3--1][2] | Need phase scope verdict | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.3.md

<!-- sase:referenced-by:end -->
