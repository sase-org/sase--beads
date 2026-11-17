# Bead: sase-1t3.11 — Replace whole-file log caches with targeted queries

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.11` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

bounded-log-caches: replace the module-level full-file materializations of the artifact index, artifact and memory read logs, bead touches, and stranded-report parses with targeted indexed or streamed queries, in census order.

## Notes

[2026-11-17T17:27:09Z · sase-1t3.11] PLANNING: Inspected sase 487825956a and pinned/opened sase-core d20108657804cfc257342b0bfb4617ea8bc61a0f, parent design, and completed sase-1t3.9 census. No prior attempt notes or landed replacement found. Artifact-file, memory-read, artifact-read, touch, and legacy-view full-source caches remain. Existing Rust bead list already uses its SQLite read model, so stranded work must remeasure and avoid building another index. Authored child epic sase_plan_bounded_log_queries.md with six medium phases in census order: artifact_files, memory_reads, bead_touches, artifact_reads, stranded_reports, verify_retention. Core filtering must precede Python conversion; plan preserves query semantics, cache invalidation, and parent decisions with no memory edits. Validation passed with --explain and again without it, both zero warnings. epic-symbols currently has no entries. Implementation and closure remain with the approved child work and its land agent; no source files changed in this planning turn.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.9](sase-1t3.9.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) | [sase-1t3.11](sase-1t3.11.md) | 0 |
