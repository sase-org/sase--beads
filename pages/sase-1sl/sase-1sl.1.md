# Bead: sase-1sl.1 — sase-core: capacity-only scan cost scales with live records, not archive size

[Bead Pages](../README.md) / [sase-1sl](README.md) / sase-1sl.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1c0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1c0.md) · **Assignee:** `sase-1sl.1` · **Size:** large
**Created:** 2026-11-12 16:45:04 EST · **Closed:** 2026-11-13 00:24:46 EST
**Plan:** [202611/capacity\_scan\_tui\_runaway.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_tui_runaway.md)

## Description

core-capacity-scan: in the linked sase-core repo, add a statx-only live-marker precheck plus meta-light closure classification (and, per the verdict_cache decision, a sticky never-live verdict cache) to the capacity_only scanner path, with parity tests and a scan-cost bench guarding identical retained records.

## Notes

[2026-11-13T05:43:53Z · sase-1sl.1.1.land] Closeout evidence (the child epic close recorded this phase closed as delegated work landed at 05:24:46): completed Rust capacity projection, persisted v2 cache, parity and archive budget work is confirmed against plan:202611/capacity_scan_core.md. Repaired cache coverage for overlapping full/exact/filtered writers with per-worker legacy parity and valid pre-repair cache inspection, plus independent rejection of a valid cache whose root identity alone changed. Verified just fmt, all 15 capacity_cache_tests, and core sase tool run check 9b51ea06bb7129f25807eb397c094d27 (exit 0, succeeded); just symvision exited 0 with all public/private symbols used. Symvision rebuilt the linked core wheel; its LSP refresh logged sccache reset and temporary install-path errors but continued and completed. This is the already-triaged distinct sccache failure tracked as sase-1sp, not new scanner work. Both master tips refreshed with no drift (core bab59781, sase 4a4ee98c65), and epic-symbols audit was empty. Existing benchmark evidence at containing production revision bab59781: 20k rows, 175 retained, 27.84x cold improvement, 876.6ms warm, 40k warm 1679.6ms. Python pin/adoption and TUI soak remain with the outer epic. This turn's remaining core change is test-only and will be committed by the host finalizer.

## Dependencies

- **Blocks:** [sase-1sl.2](sase-1sl.2.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sl.1.md) | [sase-1sl.1](sase-1sl.1.md) | 0 |
