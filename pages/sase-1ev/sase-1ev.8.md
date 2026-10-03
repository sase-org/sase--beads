# Bead: sase-1ev.8 — Rail recency glance and deleted subjects

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.8` · **Size:** medium
**Created:** 2026-10-02 14:43:15 EDT · **Closed:** 2026-10-03 02:21:06 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

rail-glance: add a right-aligned newest-change glyph and age on every Notes rail row from one subjects() plus feed() per scope. A D toggle lists tombstoned subjects in a DELETED group, each with a read-only tombstone card. Introduces the history-only rail node kind.

## Notes

[2026-10-03T06:20:33Z · sase-1ev.8] PROPOSED FOLLOW-UP: just check test-scoped fails on master with 48 failures + 7 teardown errors in pager three_panes, prompt_bar_editor_stack, macro highlight, doctor/pr/commit-report suites; tests/pager/test_app_three_panes.py + tests/ace/tui/test_prompt_bar_editor_stack.py reproduce identically (18 failed/17 passed) on clean HEAD worktree, so they are pre-existing and unrelated to rail-glance

[2026-10-03T06:20:47Z · sase-1ev.8] PROPOSED FOLLOW-UP: rail-glance PNG goldens (120x40 dark/light rail with glance column + DELETED group + tombstone card, 80x24 glance column) still wanted; prior lens phases also landed without PNG goldens, so this belongs to the launch phase full visual golden review

[2026-10-03T06:21:06Z · sase-1ev.8] rail-glance done: Notes rows gain right-aligned kit glyph+age from off-thread subjects()+feed() per scope (fail-open, width shed age-then-glyph); D toggle_deleted lists latest-is-deletion subjects newest-first in DELETED group with header N-deleted chip; tombstone cards pin deletion ordinal through existing past-card path (verified applied==ordinal, read-only refusals); history-only rail node kind added with mutation/source guards. Verified: 17 new tests + 36 keymap/rail tests + 111 lens/history/action tests pass; ruff+mypy clean on 7 touched src files; just check lint stages all pass; 48 scoped failures + 7 errors reproduce identically on clean HEAD (pre-existing, filed as follow-ups). No epic-symbols left.

## Dependencies

- **Depends on:** [sase-1ev.7](sase-1ev.7.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.9](sase-1ev.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.8/README.md) | [sase-1ev.8](sase-1ev.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8b27e3f`](https://github.com/sase-org/sase/commit/8b27e3f011019c3caad2584ddb53dc78919a8f4d) | feat(memory-history): rail recency glance and deleted subjects (sase-1ev.8) | [sase-1ev.8](sase-1ev.8.md) | 2026-10-03 02:22:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.8/README.md

<!-- sase:referenced-by:end -->
