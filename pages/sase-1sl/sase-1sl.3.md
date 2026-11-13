# Bead: sase-1sl.3 — TUI GC policy: full collections respect a duty-cycle bound

[Bead Pages](../README.md) / [sase-1sl](README.md) / sase-1sl.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1c0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1c0.md) · **Assignee:** `sase-1sl.3` · **Size:** medium
**Created:** 2026-11-12 16:45:05 EST · **Closed:** 2026-11-12 18:10:42 EST
**Plan:** [202611/capacity\_scan\_tui\_runaway.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_tui_runaway.md)

## Description

gc-duty-cycle: record each full collection's duration in gc_policy.py and defer the next full collection by last-pause times a duty factor (clamped), applying the floor to idle and backstop triggers alike, with fake-clock unit tests.

## Notes

[2026-11-12T23:10:42Z · sase-1sl.3--1] Implemented GC duty-cycle bound in gc_policy.py: records each full collection pause and defers next full by last-pause times duty factor (clamped), applied to idle and backstop triggers. Focused GC policy tests: 37 passed. Full verification sase tool run check 1b260240f986521dbf1d2d9caf7fe43c succeeded exit 0 (verdict pass). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1sl.4](sase-1sl.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sl.3.md) | [sase-1sl.3](sase-1sl.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bdf8ae1`](https://github.com/sase-org/sase/commit/bdf8ae15909f3fb61d8cb63af463183ae7a8f985) | feat(tui): bound full GC collections by duty cycle in gc\_policy | [sase-1sl.3](sase-1sl.3.md) | 2026-11-12 17:43:20 EST |
