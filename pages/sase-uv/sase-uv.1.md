# Bead: sase-uv.1 — Fresh perf baseline and durable budget benches

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.1` · **Size:** small
**Created:** 2026-08-27 12:26:43 EDT · **Closed:** 2026-08-27 14:15:56 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

baseline: capture a current-master keystroke and loader baseline, and add the benches that assert the epic's budgets so later phases have a pass/fail gate.

## Notes

[2026-08-27T18:14:49Z · sase-uv.1] Baseline captured on this host (2026-08-27, while sibling phases sase-uv.4/.5/.6/.9 ran concurrently + a just-install cargo release rebuild):

TELEMETRY (~/.sase/logs, today's records):
- tui_startup.jsonl: n=21, agents_ready_seconds p50=10.97s p95=25.01s max=25.11s (matches the plan's own 08-27 p50=11.15s claim).
- tui_agent_loads.jsonl: n=2096, load_kind full=2048 (97.7%), artifact_delta=39 (1.9%), monitor_reconcile=9 (0.4%) -- confirms the "majority full, not majority artifact_delta" budget is currently violated.
- tui_stalls.jsonl: 161 hitch/stall records through 16:52 UTC; 25 have "link" in main_thread_stack, 6 of those have last_action=="j" -- corroborates Correction 1's discovery-on-keystroke finding (a larger sample than the plan's own 61/7/5 since more time has elapsed).

WARM `load_tiered_agents` (live ~/.sase, 468 agents via artifact_index tier; host was mid cargo-build, so treat as an upper bound):
samples_ms=[1063.7, 1151.7, 1064.0, 1032.8, 1405.5], all 3.5-4.7x over the 300ms budget.
cProfile cumulative (one warm call): query_agent_artifact_index (Rust binding) 0.925s; load_workflow_agent_steps_from_snapshot 0.501s (of which enrich_agent_from_meta x1588 calls = 0.396s); load_done_agents_from_snapshot 0.177s; agent_scan_wire_from_dict 0.186s. Shape matches the plan's Correction 2 table (Rust binding ~large plurality, workflow-step enrichment the next-largest chunk).

SASE_TUI_PERF keystroke-to-paint (synthetic Pilot harness -- a live interactive `sase ace` capture isn't drivable by this agent, so this is the reproducible stand-in the runbook itself documents):
- Patches tab (50 rows): p95 ~1.7-2.8ms, well under the 16ms budget.
- Agents tab large-list (240 agents): row j/k p95 ~20-21ms (already over the tight 16ms budget purely from list scale, independent of the acute regression); J/K panel-hop p95 ~48-52ms.
- AXE/clan-fold/selected-tribe scenarios intermittently exceed their existing tight budgets on this host under load (e.g. AXE next/prev p95 24.4/18.2ms vs 16ms) -- reproduces identically on unmodified master, so this is host contention, not a regression from this phase.

Extended tests/ace/tui/bench_tui_jk.py and tests/perf/bench_tui_trace.py so budgets are asserted, not just printed (Patches tight 16ms; Agents-large-list and full-baseline jk_paint generous ceilings per the phase's own "assert a generous ceiling locally" guidance), and added the required regression-gate bench: test_bench_keystroke_reaches_no_provider_discovery_or_subprocess. It spies on resolve_artifacts_subtabs (call-counts rather than raises, since _link_follow_available swallows exceptions) and guards subprocess.run/Popen while driving 40 j/k presses on the Agents tab. Confirmed red today as designed: 116 of 40 measured keystrokes reach resolve_artifacts_subtabs(). keypath is done when this bench goes green.

`just check` passes clean on the final diff (fmt/ruff/mypy/symvision/scoped-tests all ✓).

[2026-08-27T18:15:16Z · sase-uv.1] PROPOSED FOLLOW-UP: bug — tests/test_plan_approval_launch_reliability_integration.py::test_combined_tale_approval_to_coder_link_lifecycle can hang indefinitely under host contention: an internal 'assert event.wait(timeout=5)' fails first (timeout too tight for a busy host), but the ThreadPoolExecutor.__exit__ that follows calls shutdown(wait=True) with no timeout, joining a background future that itself never completes — so the whole just-check run hangs forever instead of failing fast. Reproduced live via py-spy dump on a stuck worker (2026-08-27); unrelated to this epic (plan-approval/coder-link lifecycle, not ACE TUI). Killed the hung just-check run and re-ran clean. Needs either a shorter/robust internal timeout or shutdown(wait=True, cancel_futures=True) with its own deadline so a timing failure can't turn into an unkillable hang.

[2026-08-27T18:15:56Z · sase-uv.1] Captured a fresh current-master baseline (recorded via bead note) and extended the perf bench suite so the epic's budgets are asserted rather than merely printed.

Changes:
- tests/ace/tui/bench_tui_jk.py: added p95 assertions to the previously print-only Patches-tab (16ms tight) and Agents-tab large-list (100ms generous ceiling, per the phase's own "generous ceiling" guidance) scenarios. Added the required new regression-gate bench, test_bench_keystroke_reaches_no_provider_discovery_or_subprocess: spies on resolve_artifacts_subtabs (call-counted rather than raise-based, since _link_follow_available swallows exceptions) and guards subprocess.run/Popen while driving j/k on the Agents tab -- a behavioural assertion per the plan, so it can't flake. It fails today as designed (116/40 keystrokes reach discovery); keypath is done when it goes green. Also fixed a pre-existing bug in _install_link_index_fixture (missing the now-required LinkIndex.targets_by_ref argument, introduced by 5fb2189c2 earlier today) that was breaking this file's mypy check and its link-rail bench for every agent touching it.
- tests/perf/bench_tui_trace.py: added a generous 200ms p95 ceiling on test_full_baseline's jk_paint data across all fixture sizes so keystroke-to-paint is asserted there too.

Verified: `just check` passes clean on the final diff (fmt/ruff/mypy/symvision/scoped-tests all green; scoped selection picked 60/3453 files). Ran the full slow bench suite directly: my new/modified tests behave exactly as intended (Patches and Agents-large-list budgets hold; the new keypath gate fails red as designed); pre-existing AXE/clan/selected-tribe budget assertions intermittently fail under this host's current contention but reproduce identically on unmodified master, so that's host load, not a regression. Baseline numbers (tui_startup/tui_agent_loads percentiles, warm load_tiered_agents timing + cProfile table, keystroke-to-paint tables) are recorded in the bead notes above for later phases to compare against.

Filed one PROPOSED FOLLOW-UP note above for an unrelated hang discovered while running just check (tests/test_plan_approval_launch_reliability_integration.py can hang the whole suite under contention).

## Dependencies

- **Blocks:** [sase-uv.4](sase-uv.4.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.5](sase-uv.5.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.6](sase-uv.6.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.1/README.md) | [sase-uv.1](sase-uv.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a9273e7`](https://github.com/sase-org/sase/commit/a9273e768052cf4d69fed1ffd203ca1598d2dfa3) | test(ace-tui): assert keystroke-to-paint budgets and add keypath discovery regression gate | [sase-uv.1](sase-uv.1.md) | 2026-08-27 14:17:01 EDT |
