# Bead: sase-1t3.12 — Terminalize stale running rows in index maintenance

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.12` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

stale-index-rows: find out why about 12.5k index rows stay running with no done marker, and terminalize them in sase-core background maintenance using real witnesses, without changing the Agents live predicate.

## Notes

[2026-11-16T13:18:47Z · sase-1t3.12] PLANNING: Read parent design and existing Rust/Python maintenance; no earlier phase notes or implementation to resume. Read-only Rust index projection on 2026-11-16 found 23,293 rows, 12,398 running/no-done, zero running markers, and 13,012 current maintenance candidates versus a 10,000-row limit. Code confirms home-only running.json writer, oldest-first selection without a cursor, overbroad workspace-number claim protection, and no candidate PID/identity check. Contribution of each cause still needs measured classification. Authored a medium tale using the existing maintenance API, with witness-based policy, persistent fair traversal, binding/integration tests, and before/after measurements; this is planning only, no implementation or production-index mutation. No epic-symbol entries at planning time. Parent research ref was unavailable via audited artifact read; independent baseline collected instead.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.12.md) | [sase-1t3.12](sase-1t3.12.md) | 0 |
