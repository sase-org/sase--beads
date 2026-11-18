# Bead: sase-1t3.11.1.6 — Verify combined heap retention and query costs

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.6` · **Size:** medium
**Created:** 2026-11-17 12:30:57 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

verify_retention: integrate cache census coverage, compare retained objects and query latency on fixed workloads, and prepare evidence for the child epic land agent.

## Notes

[2026-11-18T06:26:05Z · sase-1t3.11.1.6--2] Combined retention verification — 2026-11-18

Reproduction and versions: workspace HEAD 88431cab71; Python 3.14.7; sase-core revision 71c59dca5790d8ac7e8eab1e9c1e11f8d2ae4440; Linux 6.12.117+deb13, 64 CPUs. Host load at evidence recording (01:25 EST): 15.57 / 34.04 / 38.52. `just fix` passed (20.4 s). `.venv/bin/pytest -q tests/ace/tui/util/test_gc_policy_census.py --confcutdir=tests/ace/tui/util` passed 13 tests (3.65 s); the preceding focused source lane passed 10 tests covering large histories, matching-object counts, source append/replacement and equal-size/mtime replacement. `sase bead epic-symbols sase-1t3.11.1.6` reported no entries. Existing proposed follow-ups on .2–.5 were left unchanged.

Source-lane before → after:
• Artifact index: full index materialization → Rust filters before Python conversion; a 50k-unrelated-row probe produced zero unrelated Python constructions. Result cache cap: 128 entries, 1,024 rows and 256 KiB per entry. Live census: 3 association rows.
• Memory reads: full-log snapshot → streamed audit query and bounded caches (128 keys × 50 rows = 6,400 max); 25k/100k histories passed. Live census: 3 retained events.
• Touches/views: full per-project touch and view snapshots (20,003 BeadTouch objects per full query) → exact-member queries; 20k unrelated touches + 5k views retained 1 selected touch (cold 102 ms, warm hit 0.2 ms). Live census: 0 touch rows.
• Artifact reads: full-log snapshot → streamed audit query and bounded caches (128 × 50 = 6,400 max); 30k/100k histories passed. Live census: 0 read events.
• Stranded reports: 2,824 full Issue hydrations (including 1,140 plans and ~715k description chars), 2.95 s/report → 260 candidate/context slim rows, zero heavy payload, 0.034 s snapshot and 2.36 s/report. Live census: 4 reports.

Representative core transient-memory probe (repro: generate a 100,000-row memory_reads.jsonl in a separate writer process, matching one row per 1,000; import sase_core_rs; record VmRSS; write `5` to /proc/self/clear_refs; call memory_audit_query(path, {members:[{artifacts_dir:/runs/target, agent_name:alpha}], limit:50, deduplicate:false}); read VmHWM): 50 rows returned in 0.732829 s; baseline RSS 25,219,072 B, peak 28,831,744 B, +3,612,672 B. This peak is the isolated query-call process after extension import, including Rust work and Python wire decoding; it is not a Rust allocator-only counter.

Separate TUI census: temporary `sase tui -x -t agents` in tmux window @13, PID 3005264, with the opt-in JSONL census, observed for the requested 620 s lane; the process had 1,298.9 s uptime at the last sample. Two survivor scans 10m42s apart: garbage 331,017 / 92.4 MB then 231,618 / 66.9 MB; survivors 640,355 / 94.0 MB then 734,523 / 132.9 MB. Census duration 2.72 s then 3.31 s. Final known-cache census had 11 owners. The changed log owners were bounded result/context caches only: artifact-read events/context 0/0 rows; memory-read events/context 0/3; touch events/context 0/0. No `_artifact_reads_snapshot_cache`, `_bead_touches_snapshot_cache`, or `_bead_views_snapshot_cache` owner appeared. Other current owners: artifact-file association 3 rows (128/1,024/256 KiB caps), stranded reports 4/64, artifact snapshot 846 records in 2/8 entries, glossary 16/400, skill-use 1,895 rows in 1/8 entries. The skill-use cache and other agent/UI objects are outside these five source lanes.

TUI runtime limits: RSS ranged 1.45–2.51 GB (last 2.28 GB); swap 0–822 MB (last 763 MB); allocated blocks 6.25–8.74M (last 7.78M). Executor: 32 configured workers, 17 threads, queue 0, never saturated. 20 generation-2 pause events ranged 0.808–2.347 s. These are whole-process heap/RSS observations, not attributable solely to the targeted caches. Host load was elevated and only sampled at evidence-recording time, so no controlled CPU comparison is claimed. The temporary @13 window and `/tmp/sase_27_retention_combined_stalls.jsonl` were stopped/removed after summarization. Full `sase tool run check` remains the final verification gate.

[2026-11-18T06:58:48Z · sase-1t3.11.1.6--3] Verification recovery: required ToolRun d9ad4b37754877e9d97c9322dfc9fa0a failed the full test lane (61,862 passed, 18 skipped, 2 failed). New failure: tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_with_young_index_lock_is_bounded measured 4.12s cleanup against a 2.0s assertion; test_pre_expand_parallel_no_embedded_workflows was KNOWN. The check saw host load averages 20.24/35.91/38.81 on 64 CPUs. On the unchanged tree, two focused runs of `sase tool run test -- tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_with_young_index_lock_is_bounded` passed in 8.457s and 8.847s. This supports a load-sensitive failure; a fresh required `just check` is still needed to establish completion.

## Dependencies

- **Depends on:** [sase-1t3.11.1.5](sase-1t3.11.1.5.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.1.6.md) | [sase-1t3.11.1.6](sase-1t3.11.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`81e124e`](https://github.com/sase-org/sase/commit/81e124eca85a9f0a369fb3fb3382c18406e676bd) | perf(tui): verify bounded log retention | [sase-1t3.11.1.6](sase-1t3.11.1.6.md) | 2026-11-18 02:30:41 EST |
