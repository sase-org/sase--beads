# Bead: sase-1es.8 — Final measurements, regression gates, and docs

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.8` · **Size:** small
**Created:** 2026-10-02 08:37:55 EDT · **Closed:** 2026-10-02 23:16:48 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

perf-gates-docs: rerun the benchmark against the baseline, add the memory-ceiling and leak gates, document the performance model in the pager docs and perf runbook, and record proposed follow-ups.

## Notes

[2026-10-03T03:14:32Z · sase-1es.8] Final bench before/after (after: 2026-10-03, this host; shared-host timing is noisy). BEFORE is the sase-1es.1 master baseline 2026-10-02. AFTER reran just bench-pager for code-sparse/log-dense at 500/2k/20k + cold probes; full JSON in /tmp/pager-bench-1es8-small.json and /tmp/pager-bench-1es8-20k.json (not committed, per plan).

open mount wall / peak RSS: 500 code-sparse 1.98s/268MB -> 1.06s/112MB; 2k code-sparse 8.13s/607MB -> 0.80s/112MB; 2k log-dense 10.44s/700MB -> 2.77s/127MB (noisy host); 20k code-sparse (was: never finished scale; 1es.6 box measured ~6.2s/146MB loaded) -> build 0.075s, mount 6.04s, RSS 144MB; 20k log-dense -> build 0.066s, mount 3.23s, RSS 191MB. 20k RSS <= 350MB PASS (was 5.7GB at 20k on master).
nav keys (above floor): j/k/ctrl+d/G medians ~0-12ms at 500/2k/20k; maxes spike under load (log-dense/20k ctrl+d max 0.57s, G max 0.41s above floor). Per-key <= 5ms target: medians green, loaded-host maxes not.
label_a key: 2k 0.10s/1.51s, 20k 3.41s/0.57s CPU -> still MISSES the <= 10ms target (same miss recorded on sase-1es.6); filed as PROPOSED FOLLOW-UP.
search keystrokes: 2k chars ~20-30ms, enter ~30ms; 20k chars 21-65ms, enter ~28ms, n ~4-5ms; 0 full-corpus Texts built on the new path (see sase-1es.7 note).
leak probe: 1 of 3 live at every size -> 0 live at every size. Leak gate is now regular tests in tests/pager/test_view_leak.py (3 tests, pass).
cold path: import sase.main.pager_handler 1.56s -> 0.28s; import sase.pager.screen 1.57s -> 0.59s; pager --plain file 2.33s -> 0.81s; pty first-bytes 0.02s both (proxy counting terminal-init bytes, unchanged); plain-bead still SKIPPED (no disposable SASE_HOME bead-store fixture).
memory ceiling: new regular gate tests/pager/test_perf_gates.py (strip-cache bound while scrolling 5k lines; tracemalloc ceiling 250MB opening 20k lines, measured ~40MB) - 2 passed. Docs: Performance section in docs/pager.md, Pager bench recipe in docs/perf_runbook.md, final pointers in tests/perf/README.md.
Verified: new gates 2 passed; view_leak 3 passed; bench smoke passed; sdd canonical layout 2 passed; ruff + mypy clean on new file; just fmt applied; epic-symbols clean (no entries for this bead).

[2026-10-03T03:14:49Z · sase-1es.8] PROPOSED FOLLOW-UP: memory task to add a tui_perf.md rule - never paint a whole document into one Static (Textual renders and caches every row; use a Line-API ScrollView) - and to correct the one-big-renderable-is-virtualized misconception in the old _layout.py docstring

[2026-10-03T03:15:00Z · sase-1es.8] PROPOSED FOLLOW-UP: ACE panels the old _layout.py docstring named as using the same one-big-renderable shape (AgentFilePanel, AgentPromptPanel) likely have the same scaling problem

[2026-10-03T03:15:17Z · sase-1es.8] PROPOSED FOLLOW-UP: ACE deck widgets that call theme_changed_signal.subscribe without unsubscribing (block_rail.py, panel_chrome.py) may leak the same way the pager did

[2026-10-03T03:15:33Z · sase-1es.8] PROPOSED FOLLOW-UP: per-link wire conversion cost in the Rust document-link scan (~24us/link) would belong to sase-core

[2026-10-03T03:15:47Z · sase-1es.8] PROPOSED FOLLOW-UP: ~/.sase/perf/tui_trace.jsonl has no rotation when tracing is enabled

[2026-10-03T03:15:58Z · sase-1es.8] PROPOSED FOLLOW-UP: label-prefix key still misses the 10ms target at scale (20k: 3.41s code-sparse / 0.57s log-dense CPU; 2k: 0.10s/1.51s) - needs its own optimization pass

[2026-10-03T03:16:16Z · sase-1es.8] PROPOSED FOLLOW-UP: pager --plain bead probe still SKIPPED everywhere (no disposable SASE_HOME bead-store fixture); cold-path bead time remains unmeasured

[2026-10-03T03:16:48Z · sase-1es.8] perf-gates-docs done and verified: bench rerun recorded on bead (2k mount 8-10s->0.8-2.8s, 20k RSS 5.7GB->144-192MB, leak 1/3->0, cold import 1.56s->0.28s, plain 2.33s->0.81s); new regular gates tests/pager/test_perf_gates.py 2 passed with view_leak 3 passed and bench smoke passed; docs Performance/Pager-bench/README pointers landed; ruff+mypy clean, fmt applied, epic-symbols clean, 7 follow-ups noted for land-agent triage

## Dependencies

- **Depends on:** [sase-1es.4](sase-1es.4.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1es.7](sase-1es.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.8/README.md) | [sase-1es.8](sase-1es.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`702c8c3`](https://github.com/sase-org/sase/commit/702c8c3167432347cc2800629a947f3ddaa4bdad) | perf(pager): finalize measurements, regression gates, and docs (sase-1es.8) | [sase-1es.8](sase-1es.8.md) | 2026-10-02 23:18:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0vd][1] | Check phase deps and notes to assess conflict with three-pane split work | 1 |
| read-by | [agent:sase-1es.8][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0vd/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.8/README.md

<!-- sase:referenced-by:end -->
