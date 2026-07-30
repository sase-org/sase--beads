# Bead: sase-b3.6 — Reachable, bounded, per-kind payload catalogs

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.6

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.6` · **Size:** medium
**Created:** 2026-07-30 08:18:35 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

catalog: load document payloads per document role with per-role caps instead of one shared 500-row cap, drop the prompt corpus from the warm, and memoize the payload index plus row metadata per project and kind so keystrokes do no O(rows) Python work.

## Dependencies

- **Depends on:** [sase-b3.2](sase-b3.2.md) ✓
- **Depends on:** [sase-b3.4](sase-b3.4.md) ✓
- **Blocks:** [sase-b3.7](sase-b3.7.md) ◐
