# Bead: sase-1dr.8 — Word-diff view and change navigation

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.8` · **Size:** medium
**Created:** 2026-09-30 19:09:30 EDT · **Closed:** 2026-10-01 08:14:50 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

diff-view: add the `=` read/diff toggle. The diff view shows inline word insertions and struck-through deletions, a frontmatter semantic block, and folds of unchanged runs that expand in place from a label. `[` and `]` jump between changes in both views. The default view depends on how the user arrived and then sticks for the session. `yy` copies a unified diff, and the CLI `-d` opens this view. Add visual goldens.

## Notes

[2026-10-01T12:14:09Z · sase-1dr.8] PROPOSED FOLLOW-UP: just check stays red on 4 pre-existing symvision unused-public items — HandoffSubmitResult, StarterResolution, owner_ref are tracked by task sase-1dn, while fit_next_word_ghost (ace next-word completion) has no tracking task; all 4 reproduce identically on the clean base tree

[2026-10-01T12:14:50Z · sase-1dr.8] diff-view done and verified: = read/diff toggle (arrival default, session-sticky), inline word inserts/deletes, frontmatter semantic block, fold labels that expand from their jump hint, [/] change jumps in both views, yy copies unified diff, CLI -d opens the diff view, 8 inspected diff goldens. Verified with 11 builder unit tests, 5 pilot tests (=, [/], fold expand, sticky steps, yy branches), 3 real-repo provider/CLI tests incl. core comparison render, 1 chrome test; 66-test focused set green; targeted visual file check-clean (20/20). Full just check via sase tool run is green except 4 symvision unused-public items that reproduce identically on the clean tree (3 tracked by sase-1dn, fit_next_word_ghost recorded as PROPOSED FOLLOW-UP). No epic-symbol entries remain. Fixed en route: clean-now diff keeps the now pin (never claims past unprompted), = during discovery queues instead of asking for retry, sticky re-apply runs after the read swap, read-view gutter marks suppressed in diff view.

## Dependencies

- **Blocks:** [sase-1dr.10](sase-1dr.10.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.6](sase-1dr.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.9](sase-1dr.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.8/README.md) | [sase-1dr.8](sase-1dr.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7884ffe`](https://github.com/sase-org/sase/commit/7884ffe854e52e7ff7d39d56eb3cfb8e82197dd3) | feat(sase-1dr.8): word-diff view and change navigation | [sase-1dr.8](sase-1dr.8.md) | 2026-10-01 08:18:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.8][1] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.8/README.md

<!-- sase:referenced-by:end -->
