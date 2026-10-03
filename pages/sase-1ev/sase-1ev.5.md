# Bead: sase-1ev.5 — Word-diff view on the card

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.5` · **Size:** medium
**Created:** 2026-10-02 14:43:10 EDT · **Closed:** 2026-10-02 22:24:13 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

card-diff: = toggles a sticky read/diff view rendered with build_diff_body. It covers past versions, latest change at clean now, pending edits at dirty now, creations, and tombstones. Includes cached committed comparisons, prefetch, H carrying the view, and the publish-loop test.

## Notes

[2026-10-03T02:13:40Z · sase-1ev.5] card-diff verified: 19 new tests in tests/ace/tui/modals/test_memory_pane_diff.py pass (endpoints past/clean-now/dirty-now/first-version/tombstone/hidden-skip, publish-loop endpoint walk (2,3)->(3,0)->(3,4), sticky toggle + pane-open reset, last-wins worker guard, failure-keeps-read toast, now-never-memoized, H carry view+base); 53 passed incl. time + keymap suites; ruff + mypy clean; MemoryPane imports. Endpoints via kit moment diff (never re-derived). Deviations: card folds keep kit "expand" label fixed (H opens pager to expand); now-target compare_base passes through build_history_document until timeline-lens adds explicit_base (default pager endpoints coincide).

[2026-10-03T02:14:01Z · sase-1ev.5] PROPOSED FOLLOW-UP: card-diff visual goldens — capture Admin Center past-diff, dirty-now pending diff, clean-now latest change, first-version diff at 120x40 dark/light plus 80x24 past diff

[2026-10-03T02:14:12Z · sase-1ev.5] PROPOSED FOLLOW-UP: card-diff perf budget — measure warm = step p95 (target <=30ms) and j/k p95 with SASE_TUI_TRACE=1 plus stall log during rapid toggling

[2026-10-03T02:23:23Z · sase-1ev.5--1] PROPOSED FOLLOW-UP: just check lint (feature flags) rule 7 fails identically on clean HEAD tree — closed flag bead sase-1ey still has surviving three_pane_splits definitions in registry/layout/split/pager (touched by sase-1eu.8 unflag-docs claim, unrelated to sase-1ev.5 card-diff diff which touches no flag files)

[2026-10-03T02:24:13Z · sase-1ev.5--1] card-diff done: 19 new tests in test_memory_pane_diff.py, 53 passed incl time+keymap suites, ruff+mypy clean; just check red only on pre-existing rule 7 (closed sase-1ey/three_pane_splits fails identically on clean HEAD, recorded as PROPOSED FOLLOW-UP); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1ev.4](sase-1ev.4.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.6](sase-1ev.6.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.5.md) | [sase-1ev.5](sase-1ev.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba91bf9`](https://github.com/sase-org/sase/commit/ba91bf93c12bfdee6ddd1560516292ab43b8df00) | feat(ace): add memory pane diff, history, and time views | [sase-1ev.5](sase-1ev.5.md) | 2026-10-02 22:26:30 EDT |
