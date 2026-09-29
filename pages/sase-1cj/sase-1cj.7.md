# Bead: sase-1cj.7 — Explicit next\_word menu and word-end fallback

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.7` · **Size:** medium
**Created:** 2026-09-29 07:14:33 EDT · **Closed:** 2026-09-29 13:46:14 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

next-word-menu: when a chain is armed but no ghost can be shown, Ctrl+T opens a next_word menu (context title, confidence meter, continuation preview) whose accept continues the chain; add the word-end fallback where current-word completion finds nothing, plus Ctrl+D forget.

## Notes

[2026-09-29T17:45:50Z · sase-1cj.7] PROPOSED FOLLOW-UP: just check patch/stitch terminology gate fails identically on clean base (linked sase-core at_bearing_notes.jsonl fixture hits + missing sidecar repos in env); no hits in phase files

[2026-09-29T17:46:14Z · sase-1cj.7] Rows 3/4b + forget done: next_word menu (context title, violet meter, continuation preview) opens on armed chain with no ghost and at prose word ends with no current-word candidate; accept inserts separator and re-arms; Ctrl+D forgets via deletions store; blocked contexts hint only. Verified: 17 new tests pass, widgets head+tail green (543+545), focused prediction/config suites 70 pass, 2 new PNG goldens inspected (glyph ok), symvision clean, just check green except pre-existing terminology failure identical on base (filed as follow-up)

## Dependencies

- **Blocks:** [sase-1cj.11](sase-1cj.11.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.6](sase-1cj.6.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.8](sase-1cj.8.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.7/README.md) | [sase-1cj.7](sase-1cj.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da74c11`](https://github.com/sase-org/sase/commit/da74c110de7e0df889458ec482a8b4052301ee6e) | feat(ace): explicit next-word menu and word-end fallback for sase-1cj.7 | [sase-1cj.7](sase-1cj.7.md) | 2026-09-29 13:48:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.7/README.md

<!-- sase:referenced-by:end -->
