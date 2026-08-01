# Bead: sase-da.4 — Contention-resilient task and epic bead launches

[Bead Pages](../README.md) / [sase-da](README.md) / sase-da.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r5/README.md) · **Assignee:** `sase-da.4` · **Size:** small
**Created:** 2026-08-01 13:04:26 UTC · **Closed:** 2026-08-01 14:24:32 UTC
**Plan:** [202608/bead\_store\_lock\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_store_lock_contention.md)

## Description

launch_retry: classify store-lock expiry as a distinct retryable failure, retry bead-work preclaims within a bounded budget, and report contention to the operator as a wait rather than a bare exit-code-1 error.

## Notes

[2026-08-01T14:23:47Z · sase-da.4] PROPOSED FOLLOW-UP: `just _lint-pyscripts` fails on clean master — "[Rule 2] Closer dir: tools/sase_bead is referenced by tests/ace/tui/widgets/test_agent_display_clan_context_hints.py, but tests/ace/tui/tools/ exists"; blocks `just check` for every agent.

[2026-08-01T14:24:02Z · sase-da.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough is flaky under parallel `just test` (failed in a full run, passes in isolation).

[2026-08-01T14:24:32Z · sase-da.4] launch_retry landed: new src/sase/bead/_store_contention.py classifies core lock_timeout as the one retryable launch failure (the core takes the lock before touching the store, so nothing was written), retries with a 3-attempt jittered-backoff budget, prints an operator-facing wait naming the holder read from <beads_dir>/.bead-mutation-lock.holder, and raises BeadStoreContentionError with the holder plus the exact 'sase bead work <id>' resume command when the budget is exhausted. Wired into the task preclaim (cli_work_task.proj.update) and the epic mark_ready + preclaim_epic_work (cli_work_handler), each single atomic Rust mutations so whole-call retry is safe; BeadStoreContentionError joins the existing except clauses so the epic path still runs rollback_work_launch. claims.py now reuses the shared classifier instead of its private duplicate. Verified: 7 new tests in tests/test_bead/test_cli_work_store_contention.py (retry succeeds after one simulated expiry; exhausted task budget leaves status=ready/unassigned and reports holder+resume; exhausted epic budget rolls back is_ready_to_work with phases untouched and no spawn; non-lock failures are not retried; unreadable/malformed holder metadata degrades). just fmt/lint(ruff,mypy,keep-sorted)/symvision clean; just test 25242 passed with one unrelated pre-existing flake (ace test_inline_metadata_search_commit_repeat_q_and_passthrough, passes in isolation) and just _lint-pyscripts fails identically on clean master — both noted as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-da.1](sase-da.1.md) ✓
- **Blocks:** [sase-da.5](sase-da.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-da.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-da.4/README.md) | [sase-da.4](sase-da.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`09c1d0d`](https://github.com/sase-org/sase/commit/09c1d0d6b793cc278a644bdbde4aa05c08c58148) | feat(bead): retry bead-work preclaims on store-lock contention | [sase-da.4](sase-da.4.md) | 2026-08-01 14:25:33 |
