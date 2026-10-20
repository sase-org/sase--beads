# Bead: sase-1nf.13 — Measure and attribute the TUI GC freezes on restarted TUIs

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.13

**Status:** ○ open · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Size:** medium
**Created:** 2026-10-20 13:36:16 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

gc-measure: have the user restart their TUIs onto the instrumented code, capture busy-hour and 4-hour windows on both Python versions, attribute garbage and survivors by type and producer, correlate long pauses with swap, and report against sase-1f3's targets.

## Notes

[2026-10-20T19:30:51Z · sase-1nf.13] gc-measure partial progress 2026-10-20: verified gc-instrument at HEAD aae7eae667 (source_revision reader, census flag SASE_TUI_GC_CENSUS, freeze_report --acceptance all present and working). Pre-restart baseline: athena (py3.14.7) all retained instances FAIL sase-1f3 (idle p95 1.4-3.2s vs 500ms, GC 6-15% vs <3%, hitches 2-6.3% vs <0.5%, RSS +1.6-3.9GiB, swap up to 329MiB); apollo (py3.12.3) also multi-second idle collections (e.g. p95 0.874s, GC 2.38-4.23%). Zero tui_gc_census rows on either host. BLOCKED on: (1) installed code predates instrumentation -- primary checkout /home/bryan/projects/github/sase-org/sase is at 682e52fc71 with 0 source_revision refs, and both TUIs run old code (0 startup rows carry source_revision; athena TUI pid 2720414 since Oct17; apollo pid 554302 old). Landing/host update must deliver aae7eae667 to the installed TUI first. (2) user must then restart TUI(s) with SASE_TUI_GC_CENSUS=1; confirm via startup rows carrying source_revision. (3) then wait 20+ min, capture busy-hour + 4h windows per host via monitor, attribute garbage/survivors by type+producer, correlate pauses with fault deltas/VmSwap, write report to research sidecar 202610 dir, attach via sase bead ref add, and close sase-1f3 noting the 24h soak moved to gc-fix acceptance (gc_soak=no). Bead left OPEN; nothing closed.

[2026-10-20T19:31:50Z · sase-1nf.13] gc-measure recheck 2026-10-20 (2nd pass): still blocked, state refined. Athena primary checkout still at 682e52fc71 (0 source_revision refs) and TUI pid 2720414 (since Oct17) predates instrumentation; needs installed-code update past aae7eae667 THEN restart with SASE_TUI_GC_CENSUS=1. Apollo differs: its checkout IS at aae7eae667 (source_revision reader present) but its TUI has not restarted onto it (0 startup rows carry source_revision); apollo needs restart-with-flag only. Census rows still 0 on both hosts; SASE_TUI_GC_CENSUS unset on athena. Pre-restart acceptance baselines stand (see prior note). Next runner after user acts: confirm startup rows carry source_revision, wait 20+ min, capture busy-hour + 4h windows per host via monitor, attribute, report to research sidecar 202610 dir, ref-add, close sase-1f3 noting soak moved to gc-fix (gc_soak=no). Bead left OPEN; nothing closed.

[2026-10-20T19:35:47Z · sase-1nf.13] gc-measure recheck 2026-10-20 (3rd pass): still BLOCKED — Q1 "Both restarted" does not match observed state. Athena: primary checkout 682e52fc71, installed 682e52fc7, TUI pid 2720414 (since Oct17); 0 source_revision rows in tui_startup.jsonl, 0 tui_gc_census rows, no SASE_TUI_GC_CENSUS in TUI environ — needs installed-code update past aae7eae667 THEN restart with SASE_TUI_GC_CENSUS=1. Apollo: checkout+installed at aae7eae667, but TUI pid 554302 (since Oct15) never restarted; only latest startup row f92735c0 (19:33Z) carries source_revision, 0 census rows, no census flag in environ — needs restart-with-flag only. Pre-restart acceptance baselines stand (tools/tui_freeze_report --acceptance on athena still overall FAIL: idle p95 1.4-3.2s, GC 9-13%, hitches 3.6-6.3%, RSS +1.5-1.8GiB, swap up to 329MiB). Next runner after user acts: confirm startup rows carry source_revision on both hosts, wait 20+ min, capture busy-hour + 4h windows per host, attribute, report to research sidecar 202610 dir, ref-add, close sase-1f3 noting soak moved to gc-fix (gc_soak=no). Bead left OPEN; nothing closed.

## Dependencies

- **Depends on:** [sase-1nf.12](sase-1nf.12.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.14](sase-1nf.14.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.13.md) | [sase-1nf.13](sase-1nf.13.md) | 0 |
