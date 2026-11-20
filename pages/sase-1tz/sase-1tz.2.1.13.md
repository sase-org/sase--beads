# Bead: sase-1tz.2.1.13 — Measure the combined TUI result and settle the TUI task beads

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.13` · **Size:** small
**Created:** 2026-11-19 11:13:29 EST · **Closed:** 2026-11-20 06:39:51 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

tui_acceptance: run the TUI benches and a comparable soak, then record before/after max GC pause, max stall, and peak RSS on sase-1tz.2. Close sase-1nc, sase-1gf, or sase-lx only on demonstrated resolution.

## Notes

[2026-11-19T22:53:06Z · sase-1tz.2.1.13] Acceptance run 2026-11-19 on HEAD 225bfb7ff2: .venv/bin/python -m pytest -s -m slow tests/ace/tui/bench_tui_jk.py = 8 failed / 11 passed in 582.76s; repeat against clean-base failures already tracked by sase-1nc (GC), sase-1gf (stall rows), and sase-lx (selected tribe p95). Additional current failures include archive warm-open 110.1ms vs 100ms, Fleet scenarios, and Axe sample attribution. .venv/bin/python -m pytest -s -m slow tests/perf/bench_tui_trace.py = 1 failed / 6 passed in 79.45s; failure is deterministic test/code mismatch: test stub returns (None,{}) but project_clan_tree dereferences wave_summary.layered. PROPOSED FOLLOW-UP: Update the large-roster legacy projection benchmark or adapter contract so its intentional no-wave stub is accepted — tests/perf/bench_tui_trace.py::test_warm_clan_wave_projection_large_roster_stays_near_legacy.

[2026-11-20T11:38:12Z · sase-1tz.2.1.13] Soak acceptance 2026-11-20 (comparable soak the earlier run lacked). Build 49b96a9c50 = stall_telemetry+gc_policy+ui_io_offload+ui_cpu_caches, NOT heap_retainers (225bfb7ff2). tools/tui_freeze_report --acceptance -j, post-warmup windows, mostly idle overnight (no busy hour => busy_hour/jk_p95/prompt_activity INCOMPLETE). athena 01f377a7 (Py3.14.7, 12.2h contiguous): coverage PASS, GC share 2.21% PASS, hitch share 0.12% PASS, near-input gen2 PASS; FAIL idle full p95 0.857s (limit 0.5), 1 unexplained late hitch, RSS growth 2.38GB/4h, VmSwap max 974.6MB. Gen-2: idle n=20 max 0.952s; backstop 2.276s; rss_backstop 10.891s (long-idle deep); automatic n=3 12.015/11.911/18.941s on asyncio worker threads (6.4-11.2M collected); max stall 20.166s (gc overlap 19.1s); peak RSS 5.69GiB, allocated blocks max 29.6M. apollo f9fc07ea (Py3.12.3, 12.6h): coverage/GC 1.34%/hitch 0.057%/near-input/VmSwap 0 PASS; FAIL idle p95 0.741s, 1 late hitch, RSS growth 633MB/4h; gen-2 idle n=434 max 1.503s, rss_backstop 7.823s; max stall 8.607s (gc overlap 7.84s); peak RSS 3.32GiB. ui_io_offload targets (launchable_mru_tick, hijack _canonical_path, load_project_alias_map) n=0 on both hosts since install (apollo before n=2/104/143, low-GC max 116.8s). HEAD fb85972f27 bench re-run (load 8.6/64): clan fold p95 all <16ms but stall gate fails on a prompt_activity row; link-rail fails on a clean tui_memory_heartbeat row; selected tribe L1 next/prev p95 71.8/62.4ms (budget 40). bench_tui_trace still 1 fail / 6 pass, same node. HEAD itself installed 2026-11-20 (athena 477637e5 06:12 EST, apollo df9973ba 11:25Z): too young to measure. Reports: 🔒 athena\_01f377a7\_acceptance.json 🔒 apollo\_f9fc07ea\_acceptance.json

[2026-11-20T11:38:27Z · sase-1tz.2.1.13] PROPOSED FOLLOW-UP: GC policy swap gate keys on VmSwap level, so residual swap defers every policy sweep for hours and CPython automatic gen-2 then pauses 12-19 s — athena 01f377a7: VmSwap stayed above SWAP_BYTES_PRESSURE_THRESHOLD (16 MiB, 40-938 MiB) from 18:24 to 06:11 with major_faults_per_s 0.0, emitting 698 tui_gc_memory_pressure reason=swapping deferrals (backstop 685, rss_backstop 9, idle 4); the only gen-2 collections afterward were automatic (12.0/11.9/18.9 s, 6.4-11.2M objects, asyncio worker threads), giving the 20.2 s max stall and 29.6M allocated blocks. Gate on paging rate or swap growth instead of absolute VmSwap, or bound how long pressure can defer (_gc_policy_policy.py tick/_memory_pressure). Related: rss_backstop defers as cost_unknown until 15 min long idle when no fresh cost sample exists (athena 25, apollo 22 rows).

[2026-11-20T11:38:32Z · sase-1tz.2.1.13] PROPOSED FOLLOW-UP: HEAD startup still runs multi-second main-thread file reads — apollo df9973ba (fb85972f27) in its first 10 min: low-GC pump stall 11.36 s and stall 8.00 s in ace/tui/models/artifact_files.py get_raw_prompt_content -> agent/artifact_files_cache.py read_text (_open_text/_stat_signature) and Agent.get_artifacts_dir -> _get_artifacts_dir_uncached; a 5.06 s hitch in notification_store_facade.read_notifications_snapshot -> _read_snapshot_from_rust. Same class ui_io_offload moved off the loop, but on different callers.

[2026-11-20T11:38:37Z · sase-1tz.2.1.13] PROPOSED FOLLOW-UP: (refines note #1) the bench_tui_trace large-roster clan-wave failure is pre-existing, not caused by this epic — _agent_tree_clan.py:440 dereferences wave_summary.layered since 375bceb6ea (2026-10-16, sase-1lc.8.2), while the test stub returns (None, {}); still 1 fail / 6 pass at fb85972f27.

[2026-11-20T11:39:51Z · sase-1tz.2.1.13] Verified: j/k suite 8F/11P and trace suite 1F/6P (pre-existing clan-wave stub mismatch since 375bceb6ea); three task-bead nodes re-run at fb85972f27. Comparable soak: 12-13 h tools/tui_freeze_report --acceptance on build 49b96a9c50, both hosts (athena max GC 18.9 s automatic, max stall 20.2 s, RSS 5.69 GiB; apollo 7.8 s / 8.6 s / 3.32 GiB, vs before 324 s / 331 s and 8.3 s / 116.8 s). ui_io_offload targets n=0 on both. Before/after and HEAD after-install commands are on sase-1tz.2. sase-1nc, sase-1gf, and sase-lx are not resolved; evidence notes added, left open. Follow-ups in notes #3-#5.

## Attachments

- 🔒 apollo\_f9fc07ea\_acceptance.json · application/json · 47.1455 KiB (private attachment)
- 🔒 athena\_01f377a7\_acceptance.json · application/json · 47.6543 KiB (private attachment)

## Dependencies

- **Depends on:** [sase-1tz.2.1.10](sase-1tz.2.1.10.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.11](sase-1tz.2.1.11.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.12](sase-1tz.2.1.12.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.8](sase-1tz.2.1.8.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.13.md) | [sase-1tz.2.1.13](sase-1tz.2.1.13.md) | 0 |
