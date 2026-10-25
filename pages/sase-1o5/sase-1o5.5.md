# Bead: sase-1o5.5 — Mount the QUESTIONS section on the Context card

[Bead Pages](../README.md) / [sase-1o5](README.md) / sase-1o5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.58.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.58.linker.w0.md) · **Assignee:** `sase-1o5.5` · **Size:** medium
**Created:** 2026-10-24 19:29:31 EDT · **Closed:** 2026-10-24 23:42:44 EDT
**Plan:** [202610/questions\_main\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md)

## Description

context-section: render QUESTIONS on the Context card from stubs then lane data, with the session fold heading, de-duplicate the gate row's GATE section, and add header tests, a PNG snapshot, and a j/k perf check.

## Notes

[2026-10-25T03:40:52Z · sase-1o5.5] PROPOSED FOLLOW-UP: bench_tui_jk p95 over 16ms budget on shared host (agents j/k 40-85ms) — reproduces identically on clean base tree, environmental load, not caused by QUESTIONS mount (header build micro-measures 0.28ms)

[2026-10-25T03:40:57Z · sase-1o5.5] PROPOSED FOLLOW-UP: sort_and_reorder crashes with TypeError mixing None and datetime start_time siblings (followups.sort key a.start_time or "") — found while fixture-building a pending question gate row

[2026-10-25T03:42:44Z · sase-1o5.5] QUESTIONS section mounted before OUTPUT VARIABLES from stubs then lane data with session fold heading; gate-row GATE de-duplicated (Reply phases keep presenter); 67 focused header/gate/presenter/lane tests pass; new 160x50 PNG golden double---check clean incl TZ=UTC; just check green except two KNOWN base-repro failures; no sase-1o5.5 epic-symbols left

## Dependencies

- **Depends on:** [sase-1o5.3](sase-1o5.3.md) ✓ · ⧖ 2026-10-24
- **Depends on:** [sase-1o5.4](sase-1o5.4.md) ✓ · ⧖ 2026-10-24
- **Blocks:** [sase-1o5.6](sase-1o5.6.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1o5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.5/README.md) | [sase-1o5.5](sase-1o5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2066212`](https://github.com/sase-org/sase/commit/2066212dfa5de8c57020bd604cd33f5f96196f33) | feat(ace): mount QUESTIONS section on Context card | [sase-1o5.5](sase-1o5.5.md) | 2026-10-24 23:44:30 EDT |
