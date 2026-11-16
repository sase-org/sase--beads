# Bead: sase-1t3.5 — Per-load memos for the Agents loader decode stage

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.5` · **Size:** medium
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

loader-memos: build the project alias map once per load, hoist the held-claim TTL config read, enrich each unique agent once with batch-scoped retention and artifacts-dir memos, and compute instruction-bundle file lists lazily for the detail panel.

## Notes

[2026-11-16T17:39:02Z · sase-1t3.5--1] PROPOSED FOLLOW-UP: Profile the unusually long diff-scoped test lane — while check remained active for hours, py-spy samples landed in the path-label audit walking 2,274 TUI Python files and in pytest tmp_path.find_prefixed; measure the dominant costs before narrowing tests or optimizing helpers.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.8](sase-1t3.8.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.5.md) | [sase-1t3.5](sase-1t3.5.md) | 0 |
