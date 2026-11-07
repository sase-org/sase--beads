# Bead: sase-1rq.2.1.3 — Make the test-cost lane finish inside its 180-minute timeout

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.3` · **Size:** large
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

test-cost: CI Telemetry's test-cost job is cancelled at its unchanged 180-minute timeout, about 93% through 60,399 items on 3 workers (run 42347892210). Full CI's test (3.12) runs the same items on the same 3 workers in about 61 minutes, so the cost lane's own plugins (cost recorder plus --sase-detect-global-leaks / --sase-fail-on-global-leaks) add roughly 3x overhead. Find and remove that overhead. Then make the whole recipe pass: the run, test_cost_report, and check_test_cost_budgets. Change no timeouts, budgets, or leak gates.

## Notes

[2026-11-07T18:52:39Z · sase-1rq.2.1.3] PROGRESS (subset-validated; full `just test-cost` handed to a monitor). Base b7ca9f34, Python 3.14.7 locally (CI is 3.13), 3 workers.

Root cause: the leak detector, not the recorder. Frozen subset: tests/ace/tui/modals + tests/ace/tui/actions + tests/ace/tui/models + tests/history = 3,656 items. Pytest-reported time / CPU-s per arm:
- before: fast 247.2s/541, recorder-only 244.4s/542, detector-only 684.0s/1888, cost (both) 668.3s/1827 (rc 1: 20 poisonings)
- after: fast 214.8s/498, recorder-only 230.9s/506, detector-only 361.9s/912, cost (both) 353.0s/904 (rc 0, 0 poisonings)
- cost/fast 2.70x -> 1.64x; cost-lane overhead 421s -> 138s wall and 1286 -> 406 CPU-s (~3x). Recorder contribution is immaterial in both, so CostRecorder was left unchanged.

Why: per-test cost = 2 snapshots. In dirty TUI workers (~4,000 sase modules, ~125k bindings) the binding scan + cache probe is only ~25ms; the rest was re-repr'ing large cache values every snapshot: sase.ace.testing._stylesheet_cache._CACHE (~88ms, a 2MB repr) and sase.ace.tui.util.lazy_syntax caches (up to 430ms). Snapshot was 123-603ms per call before; census after the fix: median 68-79ms, p90 86-115ms, max 124ms.

Changes:
1. tests/_global_state_leaks: exact fast paths. Snapshots are byte-identical to HEAD's (verified on 2,811- and 6,435-module states). Exact-type dispatch with a type-first check; bounded name-classification cache; import-checked cache-protocol-free builtin types; short-circuited probe (no cache_clear lookup without cache_info); per-snapshot alias memo that holds the object, so it is safe against id reuse; bounded identity reuse only for compiled patterns and frozensets of immutable scalars; cheaper container repr with a safe fallback; slots fingerprints; the diff skips unchanged names. Microbench 1.5-1.85x; in-worker A/B of snapshot CPU 1.35x before the cache fixes.
2. src/sase/ace/testing/_stylesheet_cache.py: the cached snapshot is one zlib-compressed pickle (immutable bytes, ~160KB), so the detector observes it exactly at ~1ms. AcePage hydrate dropped from ~183ms (deepcopy) to ~49ms. One pickle keeps RuleSet identity shared between rules and rules_map. 12 targeted PNG goldens are unchanged with 1 worker (11 hydrated boots).
3. tests/_conftest_runtime.py: per-test clearing of leaked caches, following the existing _reset_derived_config_caches pattern: _ASSOCIATED_PLAN_SHEET_{CACHE,SIGNATURES}, which caused all 20 subset poisonings via temp plan paths (changed-value), and the three bounded lazy_syntax render caches.
4. tests/ace/tui/modals/test_agent_action_chooser_modal.py::test_chooser_arms_enter_after_recovery_panel_opens failed once in a loaded cost run (0.3s wall-clock arm window) and passed 5/5 focused. Root-cause fix: a 30s window and an aged mount stamp, no sleep.
5. New tests: tests/test_global_state_leak_snapshot.py (18 real-snapshot tests covering same-size/nested in-place edits, rebinding/deleting/kind change, late/replaced modules, aliases with work counts, immutable-only reuse, LRU warm/clear/replace, cache APIs attached after a negative probe, broken cache APIs, probe short-circuit, env hashing, cwd/sys.path, a clean gate, xdist fail-gate aggregation, xdist report-only, id-recycling guards) and tests/test_ace_stylesheet_snapshot.py. Mutation-checked: 7/7 targeted regressions caught.

Verification: `sase tool run check` dd4ef391388cd5135dab1cd136944c56 escalated to the full suite (root conftest). All lint stages passed. 60,478 passed, 1 failed: tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim, triaged FLAKY (no_new_failures). It passes 3/3 focused on the same tree.

CI projection, not verified: Full CI test (3.13) took ~52 min including setup, versus a projected ~193 min for test-cost. A ~3x smaller detector overhead suggests roughly 95-110 min. The verify phase owns proof.

[2026-11-07T18:52:54Z · sase-1rq.2.1.3] PROPOSED FOLLOW-UP: flake — tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim — failed once in the escalated full-suite lane of sase tool run check dd4ef391388cd5135dab1cd136944c56 (14 workers, host load ~30; triage verdict FLAKY, no owner), then passed 3/3 focused on the same tree. This phase's diff does not touch the registry. Not quarantined.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.3.md) | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`578a317`](https://github.com/sase-org/sase/commit/578a317bcf98a383fbd6adf2d96a1f1e4bae2648) | perf(tests): cut test-cost leak-detector overhead about 3x without weakening the gate | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 2026-11-07 13:54:35 EST |
