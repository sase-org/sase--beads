# Bead: sase-1t3.13.1.1 — Measure the current interaction paths

[Bead Pages](../README.md) / [sase-1t3.13.1](sase-1t3.13.1.md) / sase-1t3.13.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.md) · **Assignee:** `sase-1t3.13.1.1` · **Size:** medium
**Created:** 2026-11-18 15:37:14 EST · **Closed:** 2026-11-18 15:52:46 EST
**Plan:** [202611/interaction\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202611/interaction_latency.md)

## Description

baseline: capture comparable post-heap j/k, detail-selection, unread-jump, runtime-tick, exact-delta-copy, and bead-warmup measurements; record the environment and identify which existing optimizations already meet the scope.

## Notes

[2026-11-18T20:52:20Z · sase-1t3.13.1.1] # Baseline measurements (phase sase-1t3.13.1.1, HEAD 5b08952c6d)

\## Environment (do not infer live-TUI versions from checkout)
- checkout HEAD: 5b08952c6d (plan was written against same HEAD; no drift)
- python: 3.14.7 (venv .venv/bin/python; system python3 is 3.11.13 without textual)
- textual: 8.0.1 (pinned), sase dist 0.19.0, sase import: src/sase/__init__.py (editable checkout)
- sase_core_rs import: .venv/lib/python3.14/site-packages/sase_core_rs/__init__.py
- sase-core-revision.txt: 98a22b7906f3bdcc5a9e5c293d975a9ec2c116b5
- host: athena, loadavg ~16-19 at run time, 64 cores, 64GB RAM (Mem avail ~39GB), up 3d
- roster/viewport: headless Pilot (default 80x24); fixture rosters below; cold = first call per agent per process, warm = immediate second call (bench_detail_header_summary definition)
- env flags: SASE_TUI_PERF=1 / SASE_TUI_TRACE=1 via bench fixtures (isolated tmp JSONL paths)

\## Reusable commands (all from repo root, .venv python)
- `timeout 540 .venv/bin/python -m pytest -s -m slow tests/ace/tui/bench_tui_jk_agents.py tests/ace/tui/bench_tui_jk_unread.py tests/ace/tui/bench_tui_jk_keypath.py -q`
- `.venv/bin/python -m tests.perf.bench_detail_header_summary --count 10 --output /tmp/detail_baseline.json`
- `.venv/bin/python -m tests.perf.bench_tui_trace --output /tmp/tui_trace_baseline.json`
- micro-probes (retained in shell history, not committed): /tmp/baseline_probe.py (copy_agent_graph scaling + scan ratio), /tmp/cachekey_probe.py (repr+blake2b hot-read cost)
- retained evidence: /tmp/detail_baseline.json, /tmp/tui_trace_baseline.json

\## Results

\### post-heap j/k paint (SASE_TUI_PERF key-to-paint; steady-state navigation)
- bench_tui_jk_agents (this run): Agents next p50 6.69ms p95 9.71ms max 10.71ms (n=20); prev p50 8.24ms p95 10.72ms max 12.71ms (n=20). Clan fold levels 1-2 within 16ms p95 (level 3 sample: next p50 7.76 p95 10.12 max 11.19; prev p50 8.24 p95 11.59 max 12.05).
- Verdict: ALREADY SATISFIED for steady-state j/k (p95 < 16ms). Caveat: test_bench_clan_jk_at_each_panel_fold_level FAILED on stall-log assertion (prompt_activity initial event counted as stall), not on paint numbers. Clean-tree failure, recorded as PROPOSED FOLLOW-UP below; does not block this phase.

\### detail-selection (selection chrome vs 150ms debounce vs lane completion)
- DetailPanelDebouncer = 150ms (src/sase/ace/tui/util/debounce.py); highlight paints immediately, detail deferred by design. Never count debounced completion as key-to-paint.
- bench_detail_header_summary hermetic (count 10): cold p50 memory_reads 470.8ms / artifact_reads 439.5ms / skill_uses 5.7ms; warm p50 memory_reads 3.5ms / artifact_reads 4.3ms / skill_uses 3.4ms. artifact_file_paths ~0.01ms both states (already cached/empty fixture). question_rounds cold max 6.1ms.
- trace view_hints: build_detail_header_summary.bead_touches p50 ~181ms (n=2), memory_reads p50 ~164ms, artifact_reads p50 ~100ms; agents.update_info_panel p50 0.46ms; view_hints_refresh p50 27.6ms.
- header cache key (detail_header_summary_cache_key): repr(summary)+blake2b-16 per hot lookup; micro-probe on ~61KB repr payload: p50 0.214ms p95 0.341ms max 0.357ms. Small per-hit but paid on every hint-render lookup; plan's semantic-token fix stands.
- Verdict: REMAINING. Cold enrichment is 100s of ms (expected off-thread + debounce + cache); warm is single-digit ms. Selection phase work (bounded worker, semantic token, targeted per-agent queries w/ version invalidation) is still justified.

\### unread-jump (,u bulk-ack and ,j jump branches)
- ,u: visible p50 37.53 p95 41.83; collapsed_panel p50 24.49 p95 34.96; collapsed_clan p50 42.93 p95 53.54; off_tab p50 32.93 p95 44.53 (n=10 each).
- ,j: visible p50 47.31 p95 56.83; collapsed_panel p50 44.69 p95 109.86; collapsed_clan p50 54.90 p95 127.78; off_tab p50 59.03 p95 132.66 (n=8) + agents_tab_switch 122.78/141.76 (n=2).
- Keypath guard bench passed: no provider discovery/subprocess on keystroke path (only pre-existing off-loop asyncio_3 git/gh/npm/rev-parse noted as rule-1 compliant).
- Verdict: REMAINING as regression surface (preserve immediate-selection + deferred-detail + target-panel-only expansion; fix only regressions new measurements identify). Numbers are navigation+expansion operations, not j/k paint; no 16ms budget claimed.

\### runtime-tick (periodic work)
- Code: AgentList.patch_active_runtime_rows loops whole self._agents (widgets/_agent_list_widget.py:363); _bead_warmup_candidates walks self._agents (actions/agents/_loading_bead_warmup.py:256). Confirms plan's claim.
- Trace full-baseline: refresh.auto_tick p50 ~1960ms p95 ~4497ms max ~4497ms (n=6); axe.collect p50 ~481ms p95 ~2328ms. Tick path is seconds-scale in the synthetic fixture and must stay viewport-bounded.
- Micro-probe predicate scan: full vs viewport(30): n=150 ratio 4.1x, n=600 ratio 16.3x (absolute µs-scale for cheap predicate; real resolver/aggregate calls dominate).
- Verdict: REMAINING. Viewport-aware row selection + waiter-set bounding still justified; preserve Rust interval-union semantics and cache bounds.

\### exact-delta-copy (graph preparation ownership)
- Code: own_required_apply_snapshot -> copy_agent_graph on required roots (_loading_graph.py:108); _loading_compute_merge.py normalizes relationships after merge (deleting the copy would race live UI).
- Micro-probe: copy_agent_graph full detach p50 31.6ms@150 / 126.6ms@600 (scales with roster, not delta). copy_agent_rows_relinked p50 1.6ms@150 / 7.8ms@600. Affected-closure subset copy (clan + k rows) still p50 ~31ms@150 / ~126ms@600 because clan.runtime_children fans out to all rows through the shared memo — the naive closure copy does NOT bound cost. This is the strongest evidence for the plan's conservative exact-delta path: ownership must not copy container fan-out, only genuinely mutated rows + relationship closure, with explicit trace-reason fallback.
- Which passes mutate: relationship normalization (_loading_compute_merge), slot annotation / named-proc carryover / fold-fleet projection / finalization (per plan; verified by code read, not re-timed here).
- Verdict: REMAINING.

\### bead-warmup (bead display coalescing)
- Code: _bead_warmup_candidates already coalesces off-pump and patches by identity, but collection still walks self._agents and stranded-project collection walks _agents_with_children; scheduling probes candidates before coalescing checks and worker probes again (matches plan).
- Scaling: same scan-ratio probe as ticks (4x@150, 16x@600 for predicate-only scan); real warm_* resolver calls dominate and must be bounded to surfaced rows + separately-maintained WAITING waiter set.
- Verdict: REMAINING.

\## Already-satisfied vs remaining summary
- already satisfied: post-heap steady-state j/k paint (p95 < 16ms on measured branches).
- remaining: detail-selection, unread-jump (regression surface), runtime-tick, exact-delta-copy, bead-warmup.
- no new general telemetry subsystem added (per plan constraint); reused existing benches + two /tmp micro-probes.

\## Changed paths
- None. Measurement-only phase; no repo files modified (git status clean).

\## Verification this turn
- bench_tui_jk_agents/unread/keypath: 3 passed (unread+keypath run), 1 passed + 1 failed (agents run; failure is stall-log assertion only, paint in budget).
- bench_detail_header_summary hermetic count 10: pass, JSON retained.
- bench_tui_trace full: pass, JSON retained.
- No `just check` (no tracked files changed; lint_and_test gate not triggered).

\## PROPOSED FOLLOW-UP: clan fold bench stall-log assertion trips on prompt_activity initial event
Clean-tree `test_bench_clan_jk_at_each_panel_fold_level` fails at the final stall-log gate (`prompt_activity transition=initial` counted as actual stall) while all paint p95s stay < 16ms. Either the test's actual-stall filter must exclude the initial prompt_activity event or the watchdog must not log it as a stall row. Evidence: this baseline run (HEAD 5b08952c6d), `pytest -s -m slow tests/ace/tui/bench_tui_jk_agents.py`.

[2026-11-18T20:52:46Z · sase-1t3.13.1.1] Baseline captured: env (HEAD 5b08952c6d, py3.14.7, textual 8.0.1, core 98a22b7) and j/k p50/p95/max, comma-j branches, cold/warm header lanes, delta-copy scaling, tick/warmup scan ratios recorded in bead note; j/k already satisfied, 5 lanes remain with evidence; clan-fold stall-gate clean-tree failure recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Blocks:** [sase-1t3.13.1.2](sase-1t3.13.1.2.md) ◐ · ⧖ 2026-11-18
- **Blocks:** [sase-1t3.13.1.3](sase-1t3.13.1.3.md) ◐ · ⧖ 2026-11-18
- **Blocks:** [sase-1t3.13.1.4](sase-1t3.13.1.4.md) ◐ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.13.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.13.1.1/README.md) | [sase-1t3.13.1.1](sase-1t3.13.1.1.md) | 0 |
