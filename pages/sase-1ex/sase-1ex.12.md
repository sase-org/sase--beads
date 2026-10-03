# Bead: sase-1ex.12 — Final measurements, regression gates, and docs

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.12` · **Size:** small
**Created:** 2026-10-02 14:54:00 EDT · **Closed:** 2026-10-03 11:28:40 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

acceptance: rerun the bench against the baseline and targets, and consolidate the zero-I/O structural tests. Update the perf runbook, leave live-check instructions for the user, and record follow-ups (including the `tui_perf` memory rules).

## Notes

[2026-10-03T15:26:49Z · sase-1ex.12] FINAL BENCH (bench_prompt_bar_keys.py, 2026-10-03, all phases landed; paint_ms / handler_ms) vs sase-1ex.1 baseline: first_space 321.02/280.75 -> 101.93/74.99; steady_space p50/p95 168.58/242.86 -> 114.40/143.30; single_ctrl_p 518.44/509.89 -> 32.16/0.99; burst_ctrl_p p50/p95 369.54/500.79 -> 6.55/12.17 (hdl p95 1.03); first_visit_ctrl_p 451.68/442.31 -> 16.24/0.61; stall rows 1 (baseline 0, host noise, unattributed). VERDICTS: sync handler <=~1ms everywhere (target <=5ms MET); burst key-to-paint p95 12.17ms (target <=16ms MET); first-press/first-visit multi-hundred-ms spikes GONE. SPACE TARGET MISSED: steady p95 143.30ms / first 101.93ms vs 60ms target (110ms fallback also missed) despite landed hot spare; remaining lever is the overlay-dock experiment (see follow-up note). Cold snapshot never blocks first space (blank bar + late prefill only if untouched). No budget assertions in slow bench by design (noisy host); regression gates are the structural tests. Runbook Final-results table added to docs/perf_runbook.md; tests/perf/README.md pointers finalized. No docs describe space pruning the MRU (verified by grep); nothing to correct.

[2026-10-03T15:27:03Z · sase-1ex.12] STRUCTURAL CONSOLIDATION: every acceptance checklist item exists exactly once, no duplication to remove — warm ctrl+p probe (test_launchable_mru.py), warm space probe + cold/late-prefill drop cases incl. typing/cursor/pane/dismiss (test_space_prefill.py), getter purity incl. zero stop/start/join (test_prompt_catalog.py::test_catalog_getters_never_stop_start_or_join_watcher), mount/unmount/worker once-base-first + theme parity (test_prompt_mount_dedup.py), stale-generation drop + burst pinning (test_launchable_mru.py). ADDED this phase: test_warm_cycle_ctrl_n_performs_zero_main_thread_io (ctrl+n direction was the one gap; handler is shared but the plan names both keys). Verified: 74 passed across the five files; ruff + format clean.

[2026-10-03T15:27:16Z · sase-1ex.12] LIVE-CHECK (for the user; do not restart the TUI from an agent): 1. restart the running TUI (editable installs keep already-imported code); 2. run with SASE_TUI_PERF=1; 3. press space / ctrl+n / ctrl+p and check ~/.sase/perf/tui_jk.jsonl for prompt_space / prompt_cycle_ctrl_n / prompt_cycle_ctrl_p samples; 4. confirm no ~/.sase/logs/tui_stalls.jsonl rows implicate these handlers.

[2026-10-03T15:27:31Z · sase-1ex.12] PROPOSED FOLLOW-UP: symvision PublicationPayloadFile in src/sase/core/publication_payload_facade.py fails identically on the clean base tree (verified first-hand this phase: stashed all 3 acceptance files, reran the exact check symvision argv, same 3 items incl. PublicationPayloadFile; triage labels it NEW only because the existing witness covers plan_publication_payload_batches). Pre-existing, not caused by this epic phase — owned by parent-epic notes sase-1ex #1 (sase-1es.land) and #3 (sase-1eq.3.1.land); resolve per symvision.md (wire a real consumer, privatize, or delete with tests). sase tool run check verdict new_failures is solely this item; all other lint stages and the 74 structural tests pass.

[2026-10-03T15:27:44Z · sase-1ex.12] PROPOSED FOLLOW-UP: memory task to add tui_perf.md rules (no such note exists yet): keymaps read app-owned snapshots and never validate on keystroke; getters never stop, start, or join watchers; mixins must not super-chain Textual-dispatched handlers.

[2026-10-03T15:27:55Z · sase-1ex.12] PROPOSED FOLLOW-UP: overlay-docked prompt bar experiment — the remaining lever for the missed 60ms space target (steady p95 143ms with hot spare landed); changes UX, so it needs its own bead.

[2026-10-03T15:28:09Z · sase-1ex.12] PROPOSED FOLLOW-UP: remaining on_mount doubling outside the prompt (command_line/input.py, filter_bar.py doubled _on_mount, modals/axe_entry_editor_rendering.py) recorded by sase-1ex.6 — same cooperative-hook fix applies.

[2026-10-03T15:28:20Z · sase-1ex.12] PROPOSED FOLLOW-UP: maintenance prune of stale MRU entries, if still wanted — must be concurrency-safe against record_vcs_xprompt_usage; no TUI key path calls the loader with prune=True after sase-1ex.3.

[2026-10-03T15:28:40Z · sase-1ex.12] Acceptance done: final bench rerun recorded (ctrl handler ~1ms, burst p95 12.17ms, spikes gone; space p95 143ms misses 60ms target with reason + overlay follow-up); structural tests consolidated with one added ctrl+n probe test (74 passed, ruff/fmt clean); runbook Final-results table + README pointers updated; live-check instructions and 5 PROPOSED FOLLOW-UP notes on bead. sase tool run check: only failure is symvision PublicationPayloadFile, verified byte-identical on clean base (pre-existing, parent-epic tracked).

## Dependencies

- **Depends on:** [sase-1ex.11](sase-1ex.11.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md) | [sase-1ex.12](sase-1ex.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f8c4c5`](https://github.com/sase-org/sase/commit/9f8c4c529ee997c0180a9e7036451c8a494c87c5) | docs(perf): record sase-1ex acceptance bench, gates, and runbook results | [sase-1ex.12](sase-1ex.12.md) | 2026-10-03 11:41:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.12][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md

<!-- sase:referenced-by:end -->
