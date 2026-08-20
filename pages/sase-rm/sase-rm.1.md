# Bead: sase-rm.1 — Repair core storage, wire, and concurrent bead identity defects

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.1` · **Size:** large
**Created:** 2026-08-20 14:47:48 EDT · **Closed:** 2026-08-20 16:43:26 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

core_storage: resolve Rust-core retention and wire gaps plus duplicate-ID reporting and workspace-claim parsing, then prove all four task contracts end to end.

## Notes

[2026-08-20T20:43:26Z · sase-rm.1] Implemented the approved core_storage repair contracts across sase-core and the Python repo: hidden terminal agent-artifact retention/pruning and GC reporting; BeadUpdateFieldsWire resolution present/null semantics; workspace-claim suffix preservation and fail-closed parsing; typed bead relocation publication plus created-ID resolution through create, sync, plan launch, and TUI paths. Added focused Rust/Python tests and source validators for the new public surfaces. Verification: linked sase-core cargo fmt and just check passed. Primary repo just install and just fmt passed; targeted Python suites for agent index, wire conversion, workspace claims, relocation, plan publication, sync worker hygiene, and commit-tag contract passed; just _lint-symvision passed. Final just check reached the full lane and failed only tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed after 35330 passed / 13 skipped; the exact node passed immediately in serial rerun and was recorded as +1 evidence on existing flake task sase-qp.

[2026-08-20T20:45:07Z · sase-rm.1] Implemented core storage repair contracts; verified linked core just check passed, focused Python tests passed, primary just check reached full lane and only flaked on tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed with immediate serial rerun passing; recurrence recorded on sase-qp.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.1.md) | [sase-rm.1](sase-rm.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@279f0e0`](https://github.com/sase-org/sase-core/commit/279f0e0ef7b694dd8ecadd6fae00124695b2d09a) | fix: repair core storage identity contracts | [sase-rm.1](sase-rm.1.md) | 2026-08-20 16:46:08 EDT |
| sase | [`891cf60`](https://github.com/sase-org/sase/commit/891cf604f38cd4b308245210df6443dd46d60160) | fix: propagate core storage repair outcomes | [sase-rm.1](sase-rm.1.md) | 2026-08-20 16:49:36 EDT |
