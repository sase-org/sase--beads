# Bead: sase-1t3.11 — Replace whole-file log caches with targeted queries

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.11` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

bounded-log-caches: replace the module-level full-file materializations of the artifact index, artifact and memory read logs, bead touches, and stranded-report parses with targeted indexed or streamed queries, in census order.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16
