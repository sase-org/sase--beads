# Bead: sase-1t3.11 — Replace whole-file log caches with targeted queries

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.11` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST · **Closed:** 2026-11-18 03:29:34 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

bounded-log-caches: replace the module-level full-file materializations of the artifact index, artifact and memory read logs, bead touches, and stranded-report parses with targeted indexed or streamed queries, in census order.

## Notes

[2026-11-17T17:27:09Z · sase-1t3.11] PLANNING: Inspected sase 487825956a and pinned/opened sase-core d20108657804cfc257342b0bfb4617ea8bc61a0f, parent design, and completed sase-1t3.9 census. No prior attempt notes or landed replacement found. Artifact-file, memory-read, artifact-read, touch, and legacy-view full-source caches remain. Existing Rust bead list already uses its SQLite read model, so stranded work must remeasure and avoid building another index. Authored child epic sase_plan_bounded_log_queries.md with six medium phases in census order: artifact_files, memory_reads, bead_touches, artifact_reads, stranded_reports, verify_retention. Core filtering must precede Python conversion; plan preserves query semantics, cache invalidation, and parent decisions with no memory edits. Validation passed with --explain and again without it, both zero warnings. epic-symbols currently has no entries. Implementation and closure remain with the approved child work and its land agent; no source files changed in this planning turn.

[2026-11-18T07:46:08Z · sase-1t3.11.1.land] EVIDENCE SUMMARY for sase-1t3.13 and sase-1t3.14, from child epic sase-1t3.11.1 (landing in progress; full tables are on sase-1t3.11.1.6 note #1).
The five census lanes no longer keep project-wide Python snapshots. All conversion happens in Rust (sase-core 19b89ac9, c5e60d78, 9f9341e5, 3992fce8, 71c59dca; sase pin 71c59dca). Python builds objects only for matching rows:
- Artifact index: _artifact_file_index_cache is gone. The association cache holds 128 entries, 1,024 rows, and 256 KiB per entry. Probe: 50k unrelated rows, 0 unrelated ArtifactFile objects.
- memory_reads.jsonl / artifact_reads.jsonl: both snapshot caches are gone. Streamed audit queries feed per-agent/context caches capped at 128 x 50 rows. Tested at 25k/100k and 30k/100k histories. Core transient peak: +3.6 MB on 100k rows.
- agent_bead_touches.json + bead_views.jsonl: both snapshot caches are gone. With 20k unrelated touches plus 5k views, 1 BeadTouch is retained (cold 102 ms, warm 0.2 ms).
- Stranded reports: one slim bead_stranded_snapshot replaces 2,824 full Issue hydrations: 260 slim rows, 0.034 s snapshot, 2.36 s/report (was 2.95 s).
- Separate 10-minute TUI census: no removed snapshot owner reappeared; log-lane result caches held 0-3 rows. Whole-process RSS was 1.45-2.51 GB, allocated blocks 6.25-8.74M, gen-2 pauses 0.81-2.35 s. These are not attributable to these lanes alone.
The per-agent/context loader APIs are unchanged and stat-before-query with a 0.5 s throttle, so sase-1t3.13 can key caches per agent.
Known remaining cost, being fixed by a closeout tale before this phase closes: the Rust touch member query decodes every touch before filtering, a transient +41 MB peak per cold query on the 13 MB / 16,257-touch sase index.

[2026-11-18T08:33:11Z · sase-1t3.11.1.land] EVIDENCE SUMMARY addendum for the completed touch-query tale (sase-1t3.11.1): the Rust member query now streams the JSON index through BufReader and drops unrelated rows as parsed; source identity is captured from the same open file. On the 13,137,274-byte live index with 16,257 touches, VmHWM delta fell from the triage measurement of +41,000 kB to +2,820 kB; RSS after query is +2,820 kB (was +21.7 MB), latency is 81 ms (was 57 ms), rows 0. Synthetic 6,757,137-byte index with 20,000 unrelated touches, five matches, and 1,000 signatures returned 5 rows at +3,144 kB VmHWM/RSS and 49.6 ms. Focused core tests 12/12, full sase-core check ToolRun 8fc6cc51edcd8a1eb881a8ea4100c813 passed, and all five sase touch suites passed under ToolRun c327ef58d56a76a9b3069d00ba840be5. Existing phase evidence confirms artifacts, memory reads, touches/views, artifact reads, and stranded reports use targeted or streamed queries; per-agent query shape is preserved and render paths remain stat/glob free. No --epic-symbol entries for sase-1t3.11. reported no entries.

[2026-11-18T08:33:17Z · sase-1t3.11.1.land] Phase evidence was complete with the child epic close: all five source lanes use targeted or streamed queries, per-agent query shape and render-path constraints remain satisfied, and the touch-query final transient peak is +2,820 kB on the live 13 MB/16,257-row index and +3,144 kB on a 20,000-unrelated/5-match synthetic index. Core check and all specified sase touch suites passed. No phase epic-symbol entries remain. This phase had already been settled done by the host when the completed child epic landed; this close is an idempotent confirmation only.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.9](sase-1t3.9.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) | [sase-1t3.11](sase-1t3.11.md) | 0 |
