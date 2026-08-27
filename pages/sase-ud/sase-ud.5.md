# Bead: sase-ud.5 — Durable gate execution and live output

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.5` · **Size:** medium
**Created:** 2026-08-26 14:02:54 EDT · **Closed:** 2026-08-26 18:05:46 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-exec: bind the executor's three streaming callbacks to the gate shell's gate.log through the shared bounded writer, add `sase gate answer --detach` and default shell gates to it, record the running command's pid, and write the settle-time chat file.

## Notes

[2026-08-26T22:04:22Z · sase-ud.5] PROPOSED FOLLOW-UP: sase-ud.3 (gate-shell) left two conformance gaps, confirmed pre-existing on a clean master checkout independent of this phase: (1) tests/agent/test_pending_handoff.py::test_pending_handoff_markers_are_named_constants fails because .sase_gate_pending is not added to PENDING_HANDOFF_MARKERS; (2) tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed fails because gate_shell/settlement.py:_read_meta and gate_shell/transaction.py:_read_meta are untracked marker-path-passing sites. Neither is caused by gate-exec (sase-ud.5).

[2026-08-26T22:04:43Z · sase-ud.5] PROPOSED FOLLOW-UP: sase memory init drift is pre-existing on a clean master checkout (sase/artifact_relations.json, sase/memory/sase_artifacts.md, sase/memory/README.md all show `sase init memory --check` drift), blocking `just check`s SASE validation stage and failing tests/main/test_init_memory_committed_drift.py and tests/memory/test_memory_selector_render.py::test_note_section_retains_children_listing_beneath_its_header. Not caused by gate-exec (sase-ud.5); needs an explicit sase memory init run with user approval.

[2026-08-26T22:05:06Z · sase-ud.5] PROPOSED FOLLOW-UP: tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list is not hermetic -- it reads the live host `sase bead` store instead of an isolated fixture, so it fails whenever a real bead (seen: "tmp-1") exists on the machine running the suite. Confirmed unrelated to gate-exec (sase-ud.5); also tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py has a pre-existing broken import (`_zoom_agent` from test_ace_png_snapshots_agents_zoom), which cascades into tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection via its nested `pytest -m contract --collect-only` call.

[2026-08-26T22:05:46Z · sase-ud.5] Implemented gate-exec: bound execute_gate_selection's three streaming callbacks to a gate shell's gate.log via the shared bounded writer (src/sase/gate_shell/log.py), recording the running command's pid on agent_meta.json; added 'sase gate answer --detach' (submits a supervised proc via the operation-request sidecar contract, re-invoking with --no-detach), defaulted to true for a gate whose envelope carries a shell block (bundle.envelope['shell'], the source of truth per the gate-shell design -- not the artifact-index scan, since gate-core-rs had not yet propagated gate_* scanner fields when this was written) and to false for ordinary gates; wired cli_answer._answer() to bind gate.log callbacks and call settle_gate_shell() after a successful synchronous execution; extended settle_gate_shell() to write the settle-time chat file (title, branches with the selection marked, reviewer note, per-option results, output tail) the way settle_monitor_artifacts calls save_chat_history, making #fork free for gate-fork-cli. Verified: ruff/mypy/symvision clean; just sync-completion-spec regenerated the CLI completion snapshot (also picked up pre-existing gate-shell/gate-create drift); new tests in tests/gate_shell/test_log.py, tests/gate_shell/test_settlement_chat.py, tests/test_gate_cli_answer_detach.py plus the full gate/gate_shell/gate_conformance/completion suites all pass (just test-scoped run in full: only pre-existing, unrelated failures remain, recorded as PROPOSED FOLLOW-UP notes on this bead -- sase-ud.3's pending-handoff-marker and marker-path-passing audit gaps, pre-existing sase-memory-init drift, and two non-hermetic tests unrelated to gate shells).

## Dependencies

- **Depends on:** [sase-ud.3](sase-ud.3.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.6](sase-ud.6.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.7](sase-ud.7.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.5/README.md) | [sase-ud.5](sase-ud.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`460aa87`](https://github.com/sase-org/sase/commit/460aa87863cb8355582c5bc15ecb6679464bd109) | feat(gate): stream gate-shell command output to gate.log and add answer --detach | [sase-ud.5](sase-ud.5.md) | 2026-08-26 18:06:45 EDT |
