# Bead: sase-m6.7.1.4 — Reveal as a reversible lens

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.4` · **Size:** medium
**Created:** 2026-08-16 02:53:40 EDT · **Closed:** 2026-08-16 07:56:21 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

reveal: keep the query rewrite as the mechanism but wrap it in a lens record with a visible return affordance, generalize the hard-coded Patch rewrite terms onto the contract, and make dangling targets diagnostics instead of pane invalidations.

## Notes

[2026-08-16T11:55:24Z · sase-m6.7.1.4--1] PROPOSED FOLLOW-UP: tests/test_agent_artifact_directory_operation_audit.py:292 has a ruff F601 duplicate dict key literal ("src/sase/workspace_provider/reset_replay.py:_clear_owned_paths") that blocks the whole-repo just lint/just check/just check-full gate for every agent; confirmed pre-existing on master at a0b6cd16b before this phase touched anything.

[2026-08-16T11:55:51Z · sase-m6.7.1.4--1] PROPOSED FOLLOW-UP: `sase monitor show prrwzjh1wdt8 --all-lines` failed with `ValueError: artifact record at .../artifacts/ace-run/202608/15/20260815145837 is not a monitor member`, preventing retained monitor log inspection from the handoff; monitor listing should skip or quarantine non-monitor artifact records instead of aborting.

[2026-08-16T11:56:21Z · sase-m6.7.1.4--1] Verified focused ruff and mypy on the relation-reveal touched files passed; verified `just test tests/ace/tui tests/test_relation_reveal.py tests/test_query_history.py` passed with 9216 passed and the existing 2 timer coroutine warnings; attempted `just check`, which stopped at the pre-existing unrelated ruff F601 duplicate dict key in tests/test_agent_artifact_directory_operation_audit.py:292 recorded as a PROPOSED FOLLOW-UP.

[2026-08-16T11:58:17Z · sase-m6.7.1.4--1] Verified focused ruff and mypy on touched files; just test tests/ace/tui tests/test_relation_reveal.py tests/test_query_history.py passed with 9216 passed; just check stops at the separately noted pre-existing ruff F601 duplicate dict key blocker.

## Dependencies

- **Depends on:** [sase-m6.7.1.3](sase-m6.7.1.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-m6.7.1.6](sase-m6.7.1.6.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.1.4.md) | [sase-m6.7.1.4](sase-m6.7.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`30c9ba2`](https://github.com/sase-org/sase/commit/30c9ba23b7fbfc4e8956577af3dddc49cabea270) | feat(artifacts): add reversible relation reveal lens | [sase-m6.7.1.4](sase-m6.7.1.4.md) | 2026-08-16 08:00:27 EDT |
