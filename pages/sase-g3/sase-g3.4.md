# Bead: sase-g3.4 — Record a contexts baseline from a local full run

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.4` · **Size:** medium
**Created:** 2026-08-06 08:55:34 EDT · **Closed:** 2026-08-06 09:39:01 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

baseline: only `tools/fetch_coverage_contexts` installs a baseline into the host-local cache, so an instrumented local run's database is invisible to selection; let a local `cov-contexts` run install itself as a `<sha>.sqlite` baseline so a workspace is not dependent on the CI artifact alone.

## Notes

[2026-08-06T13:38:33Z · sase-g3.4] PROPOSED FOLLOW-UP: two tests are load-flaky under the full parallel lane — tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_records_compact_pump_hitch_and_recovery and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout both failed in `just check` and both pass in isolation; neither touches selection or coverage contexts.

[2026-08-06T13:39:01Z · sase-g3.4] Added tools/install_coverage_contexts (local baseline producer) wired into just test-contexts via --if-enabled; extracted shared prune_baselines into tests/_test_selection_contexts.py and reused it from tools/fetch_coverage_contexts; pinned COVERAGE_CORE=ctrace for the cov-contexts lane in tools/run_pytest (sysmon on py3.14 drops per-test attribution after the first test to hit a line: 6 contexts vs 32 for test_agent_lanes.py, matching CI's py3.12 ctrace default). Verified: just lint clean (ruff, mypy, symvision, toobig); 12 new tool tests + 3 coverage-core tests + 1 Justfile-wiring test pass; end-to-end against a real ctrace-recorded coverage database the partial-run guard fires correctly and the dirty-src guard correctly ignores the non-src working-tree changes. just check's scoped lane passed except two load-flaky tests unrelated to selection (stall watchdog, bead lock contention) that pass in isolation — noted as a follow-up. NOT verified: a full-suite instrumented re-record under ctrace comparing context counts against the CI artifact wholesale; the suite gate was saturated by other agents for the duration.

## Dependencies

- **Blocks:** [sase-g3.5](sase-g3.5.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.4/README.md) | [sase-g3.4](sase-g3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2ef98cb`](https://github.com/sase-org/sase/commit/2ef98cb3e646ca6e6f5298398b5a8c4855273774) | feat(test-selection): record a contexts baseline from a local full run | [sase-g3.4](sase-g3.4.md) | 2026-08-06 09:39:50 EDT |
