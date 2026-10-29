# Bead: sase-1pn.4 — Make the dev toolchain deterministic across CI and workspaces (sase-1cs, sase-vr)

[Bead Pages](../README.md) / [sase-1pn](README.md) / sase-1pn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.land.md) · **Assignee:** `sase-1pn.4` · **Size:** medium
**Created:** 2026-10-29 10:44:08 EDT · **Closed:** 2026-10-29 11:32:00 EDT
**Plan:** [202610/task\_backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_2.md)

## Description

dev-toolchain: apply the toolchain_source decision so Textual, ruff and mypy resolve to one declared version everywhere, refresh uv.lock, and fix any lint findings the chosen versions report.

## Notes

[2026-10-29T15:31:28Z · sase-1pn.4] PROPOSED FOLLOW-UP: investigate scoped-suite-only test failures — ToolRun da99176eb6f2a348337b37d86f176280 marked tests/test_agent_dismiss_persistence.py::test_normal_dismiss_reconciles_unloaded_agent_session_members_after_root_delete, tests/test_axe_chop_bead_claim_checks_leases.py::test_snapshot_and_reconcile_share_one_lease_and_one_publication, and tests/test_axe_chop_bead_claim_checks.py::test_live_candidate_declined_by_terminal_bead_state_is_not_marked[Status.IN_PROGRESS] NEW once; all three passed serially on clean base cddea47cc6 and the unchanged worktree. Existing sase-1oo tracks an adjacent broad-suite claim-prepass flake; exact-node searches found no matching task. Investigate why the broad scoped lane differs.

[2026-10-29T15:31:34Z · sase-1pn.4] TASK RESOLVED: sase-1cs — Pinned Textual 8.0.1 in the dev extra to match the visual renderer pin and lock; the guard test keeps the pin aligned. Fresh no-sources .[dev], frozen uv sync, and this workspace after sase tool run install-venv all report 8.0.1. Both named Textual regression files passed (32 tests). Existing workspace venvs pick up the pins on their next just install-venv.

[2026-10-29T15:31:39Z · sase-1pn.4] TASK RESOLVED: sase-vr — Pinned ruff 0.17.3 and mypy 2.4.1 in dev, pinned format-tools Ruff, refreshed uv.lock, and added a contract test for dev, formatter, Justfile setup, and lock agreement. Fresh no-sources .[dev], frozen uv sync, and this workspace after sase tool run install-venv all report ruff 0.17.3 and mypy 2.4.1. A stale formatter venv refreshed itself to Ruff 0.17.3. just lint completed successfully; the final just check lint stages passed.

[2026-10-29T15:32:00Z · sase-1pn.4] Pinned Textual 8.0.1, Ruff 0.17.3 and mypy 2.4.1 across dev, format-tools, and uv.lock; added lock/setup contract tests. Fresh, locked, and workspace installs agree; the named Textual tests and lint pass. just check lint stages passed; three scoped test failures passed on clean base and unchanged-tree reruns, with a follow-up recorded. epic-symbols reported no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pn.4/README.md) | [sase-1pn.4](sase-1pn.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pn.3--1][1] | Need close note format from sibling phase | 1 |
| read-by | [agent:sase-1pn.4][2] | Verify the proposed follow-up and task resolution notes before closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pn.4/README.md

<!-- sase:referenced-by:end -->
