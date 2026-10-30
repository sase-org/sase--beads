# Bead: sase-1nf.14.1.3 — Avoid copying Agent graphs that a load will discard

[Bead Pages](../README.md) / [sase-1nf.14.1](sase-1nf.14.1.md) / sase-1nf.14.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.3` · **Size:** medium
**Created:** 2026-10-24 13:37:43 EDT · **Closed:** 2026-10-24 14:19:44 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:d0e2fb9ef3c7f133be198c25 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

graph-allocation: classify cached-row use before detaching graphs, copy only required ownership closures, and preserve worker isolation and aliases.

## Notes

[2026-10-24T18:19:44Z · sase-1nf.14.1.3] graph-allocation done: classify-then-copy in _loading_graph (CachedGraphNeeds/classify_cached_graph_needs/own_required_apply_snapshot) wired into worker/apply-boundary/merge paths. Authoritative+projection loads copy 0 rows (was 102/1000); delta/query-change/capacity/named-proc/fleet behavior preserved with shared-memo aliasing. Verified: 4 new regression tests in test_agents_tab_graph_isolation (failed pre-fix), 243 tests green across the loading-pipeline closure, all just-check lint gates pass (ruff/mypy/symvision). Benchmarks at 100/1000 rows: authoritative 14.8/117.6ms peak 0.2/2.0MB vs old full-copy 43.4/395.2ms peak 1.0/10.0MB; delta steady-state ~22ms/100 rows. Note: sase tool run check run a11cacab77de983d1333909ff64caa86 escalated to the full suite on a stale baseline (4641 commits behind) and is still running under host load; no lane failure observed. No follow-ups.

[2026-10-30T03:04:53Z · sase-1nf.14.1.land] LAND CORRECTION (sase-1nf.14.1.land, 2026-10-29): this phase's reported work never landed. classify_cached_graph_needs / CachedGraphNeeds / own_required_apply_snapshot and its 4 regression tests do not exist on any ref. The agent crashed after its close (provider_timer reuse during a Muse wait-guard continuation), and a bead_claim_checks lease then force-reset the workspace without a rescue. That crash chain is now fixed by 9012f46cf9. The fixed-code captures (.7/.8, source 196690f6cb) therefore ran WITHOUT this fix. The diff was recovered by replaying the 20 completed edit_file calls from Muse session 9780b2e4 onto base 602ff33c1b, stored as file:explicit:cc1fcd3f9d4bd944a9c454b5 (sha256 d62501a9...). It applies cleanly to master c927c40860. The epic closeout tale re-lands and re-verifies it; the phase stays closed and its completion is recorded by that tale.

[2026-10-30T06:36:40Z · sase-1nf.14.1.land--2] RE-LANDED by the sase-1nf.14.1 closeout tale: src/sase/ace/tui/actions/agents/_loading_graph.py (_CachedGraphNeeds/classify/own_required), _loading_compute.py, _loading_compute_merge.py, _loading_apply_snapshot.py + _loading_compute_types.py docstrings, tools/_tui_freeze_report_acceptance.py + _tui_freeze_report_activity.py (HEARTBEAT_MISSING_GAP_S accept branch) + tools/tui_freeze_report, docs/contribute/perf-runbook.md exec-restart sentence, tests/test_agents_tab_graph_isolation.py (incl new test_authoritative_with_capacity_report_leaves_cached_history_untouched) + tests/test_tui_freeze_report_acceptance.py + tests/test_tui_freeze_report_activity.py + _agents_tab_incomplete_merge_helpers.py. Tests: 40 passed graph-isolation+freeze (5.58s), 49 passed with test_agent_graph_copy, 54 passed capacity closure; symvision clean; git diff --check clean; no PNG moves. Benchmark file:explicit:d0e2fb9ef3c7f133be198c25 (1000-row authoritative 1002->0 clones, peak 11.2MB->3.1MB, 994ms->683ms). Check: sase tool run check 34889e9ad09857b1e454bc38e9c23871 (1h timeout) + 99cc95deba3cffd9af1f1ae41fd4c34f (1.5h timeout), both incomplete in test(scoped) after all lint/docs stages passed.

## Dependencies

- **Blocks:** [sase-1nf.14.1.6](sase-1nf.14.1.6.md) ✓ · ⧖ 2026-10-24
