# Bead: sase-1t3.13.1.5 — Verify combined latency and prepare parent-phase completion

[Bead Pages](../README.md) / [sase-1t3.13.1](sase-1t3.13.1.md) / sase-1t3.13.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.md) · **Assignee:** `sase-1t3.13.1.5` · **Size:** medium
**Created:** 2026-11-18 15:37:15 EST · **Closed:** 2026-11-18 18:23:37 EST
**Plan:** [202611/interaction\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202611/interaction_latency.md)

## Description

integration: repeat the baseline workload on the combined changes, verify responsiveness and graph isolation under interleaved refreshes, record evidence on sase-1t3.13, and prepare completion for this child epic's land agent.

## Notes

[2026-11-18T23:23:04Z · sase-1t3.13.1.5--1] # Combined integration verification — 2026-11-18

\## Environment and fixture

- Checkout HEAD: `194b1a1ef4175fe5397b8f666883ac9028cbcec3`; working tree clean; no tracked paths changed.
- Python 3.14.7 from `.venv/bin/python`; Textual 8.0.1 from `.venv/lib/python3.14/site-packages/textual/__init__.py`; sase 0.19.0 imported from `src/sase/__init__.py`; `sase_core_rs` 0.44.2 imported from `.venv/lib/python3.14/site-packages/sase_core_rs/__init__.py`.
- `sase-core-revision.txt` and linked `sase-core` HEAD both equal `b1a0363997eb8150f8db8a425b83564faf5101f3`. The baseline used the same Python/Textual/sase versions but core revision `98a22b7906f3bdcc5a9e5c293d975a9ec2c116b5`; cold comparisons are therefore directional.
- Host: athena, Linux 6.12.117, 64 CPUs, 62.7 GiB total and 28.9 GiB available after the run. At the first bench, load averages were 19.30/16.90/13.37; at the isolated repeat they were 6.37/9.68/12.90. Baseline recorded load about 16–19 and about 39 GB available.
- Headless Pilot defaults to 80x24. Detail benchmark used count=10 (first call cold, immediate second call warm). Full trace fixtures were 100 CS/50 agents, 500/200, and 2000/1000.

\## Commands and results

1. `timeout 540 .venv/bin/python -m pytest -s -m slow tests/ace/tui/bench_tui_jk_agents.py tests/ace/tui/bench_tui_jk_unread.py tests/ace/tui/bench_tui_jk_keypath.py -q`
2. `.venv/bin/python -m tests.perf.bench_detail_header_summary --count 10 --output /tmp/detail_combined.json`
3. `.venv/bin/python -m tests.perf.bench_tui_trace --output /tmp/tui_trace_combined.json`
4. Focused combined suite (worker/enrichment, two-phase/deferred detail, bead warmup, runtime patch/tick/compute, artifact-delta loader, delta-copy, graph isolation/merge, unread fast path): 212 passed in 9.70s.
5. Isolated diagnostic repeat: `.venv/bin/python -m pytest -s -m slow tests/ace/tui/bench_tui_jk_agents.py -k 'test_bench_agents_jk_and_panel_navigation or test_bench_selected_tribe_jk_at_each_fold_level' -q`.

\### Agents j/k and fold levels

Primary-run `next` was p50/p95/max 16.21/37.11/83.59 ms (n=19), `prev` 13.63/40.36/48.07 ms (n=19); panel cycling `next_agent_panel` 37.51/45.76/47.76 ms (n=20) and `prev_agent_panel` 54.96/65.24/70.43 ms (n=20). Baseline `next` was 6.69/9.71/10.71 ms (n=20), `prev` 8.24/10.72/12.71 ms (n=20). The ordinary j/k p95 target is missed in this combined-tree run.

Clan fold levels remained below the 16 ms p95 target (each direction n=20):

- Level 1 next 7.60/12.24/12.91 ms; prev 8.79/11.78/12.24 ms.
- Level 2 next 8.18/13.76/27.47 ms; prev 8.35/10.67/12.45 ms.
- Level 3 next 9.26/14.32/25.62 ms; prev 7.20/10.57/10.85 ms.

The new selected-tribe fold case stopped at level 1 because its 40 ms p95 guard failed: next 52.97/80.99/96.21 ms and prev 52.94/71.64/98.72 ms (n=40 each). The lower-load isolated repeat still failed: next 46.53/64.58/68.01 ms and prev 44.99/58.49/65.19 ms. Its remaining fold levels were not reached. This is a persistent miss on the combined tree; it was not clean-base compared.

The same isolated repeat measured ordinary next 15.92/20.25/61.30 ms (n=19) and prev 13.66/17.98/18.28 ms (n=19), confirming p95 remains above the 16 ms target. The baseline note's known clan-fold failure is separate: the fold p95 values pass, but the final stall-log assertion treats `prompt_activity transition=initial` as an actual stall. That failure was already reproduced on the clean baseline and recorded on `sase-1t3.13.1.1` and its parent note.

\### Unread navigation and keypath

Current comma-j p50/p95/max: visible 49.97/70.17/70.17 ms (n=10); collapsed panel 47.95/96.26/96.26 (n=10); collapsed clan 57.07/140.77/140.77 (n=10); off-tab 54.42/140.78/140.78 (n=8); tab switch 133.64/140.13/140.13 (n=2). Baseline p50/p95 was 47.31/56.83, 44.69/109.86, 54.90/127.78, 59.03/132.66, and 122.78/141.76 respectively. These are navigation/expansion operations, not j/k paint.

The keypath guard passed. It observed `git describe`, `gh api`, `npm root`, and `git rev-parse` only on asyncio worker threads, outside the keystroke path. The unread bulk-ack branches also passed (n=10 per branch).

\### Detail chrome, debounce, and lane completion

In the count-10 hermetic detail run, cold/warm p50 and max were: memory reads 478.4/530.9 ms and 3.4/3.9 ms; artifact reads 443.0/460.7 ms and 4.2/8.4 ms; skill uses 5.8/272.5 ms and 3.7/3.8 ms. Baseline p50s were 470.8/3.5 ms for memory reads, 439.5/4.3 ms for artifact reads, and 5.7/3.4 ms for skill uses. The benchmark reports p50/max, not p95; each cold/warm lane used 10 agents. `/tmp/detail_combined.json` retains the report.

The immediate detail-panel chrome span `agents.update_info_panel` was 1.23/17.44/17.54 ms (p50/p95/max, n=20) on the 2000/1000 fixture; the immediate highlight span stayed below 0.5 ms p95. The intentional 150 ms detail debounce remains in place. The `agents.refresh_debounced` span measures the handler after that delay, not the wait: at 2000/1000 it was 43.92/70.05/70.05 ms (n=2). Header lane completion is separate: `build_detail_header_summary` was 1323.52/3680.92/3680.92 ms (n=4) in that fixture; on the clan-container hint scenario it was 351.57/476.40/476.40 ms (n=3), with both cold and warm results represented. The slow-enrichment A/B/A regression test passed.

\### Runtime, warmup, graph isolation, and memory behavior

Full-trace `refresh.auto_tick` p50/p95/max was 577.55/879.99/879.99 ms (n=4) at 100/50, 771.15/1506.22/1506.22 (n=4) at 500/200, and 1939.12/2347.06/2347.06 (n=4) at 2000/1000. At 2000/1000 the baseline note reports about 1960/4497/4497 ms (n=6): current p50 is similar, p95/max lower, with fewer samples. `axe.collect` at 2000/1000 was 594.27/1837.27/1837.27 ms (n=5), against baseline about 481/2328 ms. Trace warmup spans were 3221 ms (n=1) at 100/50, 690.80/1190.07 ms (n=2) at 500/200, and 3963 ms (n=1) at 2000/1000. The trace also logged an unhandled Textual timer `ZeroDivisionError` with interval zero; the command still exited 0 and wrote its complete JSON.

The focused tests verify the resource bounds: rapid A/B/A selection kept one compute active, replaced the pending request with the latest selection, skipped B, and kept one reusable cached result; runtime patching touched only surfaced viewport rows (2 of 40 in the 8-line viewport fixture); warmup selected at most 32 of 80 historical WAITING rows per batch, covered 64 distinct rows across two batches, and kept stranded projects to at most 4 per batch. The small-delta probe used 150- and 600-row graphs with 2- and 8-row updates. Deep graph-copy rows/calls were zero, but shallow Agent copies were 150/150/600/600, while only 2/8/2/8 changed rows remained new after share-back. Thus retained rows are delta-sized, but temporary allocation still scales with the full roster. This is a measured copy/memory target miss for follow-up.

The trace harness does not report process RSS or heap heartbeats, so this run makes no long-session heap claim; the separate soak phase owns that measurement. Available host memory was 28.9 GiB at the end. No tracked source files changed, so no repo-wide check was required.

[2026-11-18T23:23:37Z · sase-1t3.13.1.5--1] Repeated combined interaction measurements and focused verification; 212 tests passed; benchmark results, environment, baseline comparisons, and remaining misses recorded on this phase and parent; epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1t3.13.1.2](sase-1t3.13.1.2.md) ✓ · ⧖ 2026-11-18
- **Depends on:** [sase-1t3.13.1.3](sase-1t3.13.1.3.md) ✓ · ⧖ 2026-11-18
- **Depends on:** [sase-1t3.13.1.4](sase-1t3.13.1.4.md) ✓ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.13.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.1.5.md) | [sase-1t3.13.1.5](sase-1t3.13.1.5.md) | 0 |
