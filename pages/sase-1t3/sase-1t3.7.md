# Bead: sase-1t3.7 — Provider-tab discovery after first paint as one generation

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.7` · **Size:** large
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

provider-discovery-deferral: build fixed-tab bindings synchronously. Publish provider tab descriptors after first paint as one coherent generation for keymaps, Artifacts composition, help, the command catalog, and navigation, avoiding the deferral traps the research lists.

## Notes

[2026-11-16T16:09:52Z · sase-1t3.7] Planning evidence at ac19f907ae: trust-root prerequisite is landed; synchronous provider discovery remains in build_app_bindings and ArtifactsView.__init__, and the view retains its original descriptor tuple while other consumers can read a refreshed cache. No earlier implementation notes existed. Fresh-process PYTHONPATH=src component probe (Python 3.14.7, Textual 8.0.1, sase-core-rs 0.44.2): app import 2.020s, construction 1.474s, provider discovery 0.603s (18 records, one issue), identity after construction 0.720s. Separate cold identity 1.140s, warm <0.001s. These are individual component observations, not latency percentiles; constructor-only session/toast registration was stubbed. Scope narrowed to first-paint protection and coherent TUI snapshots, with no shared identity rewrite. A two-phase child epic (snapshot-consumers -> post-paint-publication) passed both required validation passes with zero warnings and is being submitted for review. No implementation changed or bead closed. epic-symbols reports no entries; land agent must recheck at closure.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.4](sase-1t3.4.md) ✓ · ⧖ 2026-11-16
