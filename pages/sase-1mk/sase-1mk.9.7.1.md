# Bead: sase-1mk.9.7.1 — Bring the agent-artifact marker audits in line with the atomic done.json writers

[Bead Pages](../README.md) / [sase-1mk.9.7](sase-1mk.9.7.md) / sase-1mk.9.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.9.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.land.md) · **Assignee:** `sase-1mk.9.7.1` · **Size:** small
**Created:** 2026-10-19 00:00:09 EDT · **Closed:** 2026-10-19 00:46:02 EDT
**Plan:** [202610/ship\_v0\_18\_0\_marker\_audit\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_marker_audit_repair.md)

## Description

marker-audit: teach the marker mutation and path-passing audits about write_json_marker_atomic and review the two done.json writers e5c02dc8a4 moved onto it (task sase-1mt), so all four audit nodes pass.

## Notes

[2026-10-19T04:45:23Z · sase-1mk.9.7.1] sase-1mt is resolved by this catalog repair. Added write_json_marker_atomic to _MUTATION_CALL_NAMES. Updated mutation reviews: write_done_marker_and_update_index and write_error_done_marker now expect mutation_calls=("write_json_marker_atomic",) with lifecycle_calls=(_UPDATE_INDEX,). No other src/sase write_json_marker_atomic callers surfaced as mutation or path-passing sites (other callers write launch-admission, hold, monitor, and diagnostics files without tracked marker literals). Path-passing still flagged write_error_done_marker because it inlines Path(...) / "done.json" into the helper; added a PathPassingReview with lifecycle_coverage (writes done.json through write_json_marker_atomic then update_agent_artifact_index_for_marker_mutation). Runtime writers from e5c02dc8a4 were left unchanged; done.json readers json.load payloads so sort_keys=True is safe. Direct pytest: 15 passed on tests/test_agent_artifact_marker_mutation_audit.py, tests/test_agent_artifact_marker_path_passing_audit.py, tests/test_run_agent_runner_completion_helpers.py, tests/fakey/test_provider_drain_e2e.py. just fix clean. sase tool run check e996bbfb6e8d632139c7686cc9268d44: lint green; test (scoped) 15m31s; verdict no_new_failures — 1 FLAKY. epic-symbols empty.

[2026-10-19T04:45:45Z · sase-1mk.9.7.1] PROPOSED FOLLOW-UP: FLAKY tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess — ToolRun e996bbfb6e8d632139c7686cc9268d44 timed out the nested pytest after 180s; already tracked by sase-120; check verdict no_new_failures

[2026-10-19T04:46:02Z · sase-1mk.9.7.1] Marker audits recognize write_json_marker_atomic. write_done_marker_and_update_index and write_error_done_marker reviewed with mutation_calls=('write_json_marker_atomic',) plus _UPDATE_INDEX; write_error_done_marker also reviewed for path-passing with lifecycle coverage. Direct pytest 15 passed (mutation + path-passing + completion helpers + provider drain e2e). ToolRun e996bbfb6e8d632139c7686cc9268d44 no_new_failures (1 FLAKY sase-120). epic-symbols empty. sase-1mt catalog drift is the change this phase lands.

## Dependencies

- **Blocks:** [sase-1mk.9.7.2](sase-1mk.9.7.2.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.9.7.1/README.md) | [sase-1mk.9.7.1](sase-1mk.9.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`850b9fd`](https://github.com/sase-org/sase/commit/850b9fdfcb8e691ecf9c19926535439e84e003d8) | fix(tests): recognize atomic JSON marker writes in artifact audits | [sase-1mk.9.7.1](sase-1mk.9.7.1.md) | 2026-10-19 00:47:30 EDT |
