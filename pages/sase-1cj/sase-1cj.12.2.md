# Bead: sase-1cj.12.2 — TUI ghost, ranking gate, warm-cache fixes, and epic-symbol cleanup

[Bead Pages](../README.md) / [sase-1cj.12](sase-1cj.12.md) / sase-1cj.12.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.2` · **Size:** medium
**Created:** 2026-09-29 18:29:16 EDT · **Closed:** 2026-09-29 18:48:24 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

## Description

tui-fixes: clear the stale Textual suggestion whenever the ghost is invalidated, gate context promotion on word_ranking smart, stop the archive and empty-history rebuild loops, recompile on deletions-only changes, repair the three red next-word tests with a sturdier fixture corpus, and retire all twelve sase-1cj epic-symbol whitelist entries.

## Notes

[2026-09-29T22:47:39Z · sase-1cj.12.2] PROPOSED FOLLOW-UP: sase tool run check fails at lint (patch/stitch terminology) on sase-core note_attachment fixtures (14 defects in at_bearing_notes.jsonl) unrelated to tui-fixes; reproduce by running sase tool run check on clean base

[2026-09-29T22:48:24Z · sase-1cj.12.2] tui-fixes done: stale ghost clears Textual suggestion; context promotion gated on word_ranking smart; archive built_at set on every attempt empty-history treated as built deletions recompile history inventory bounded to 6 months with month= log once; 8-row fixture restores 2-word balanced ghost; 12 sase-1cj epic-symbols retired via privatization plus 3 pragmas; verified 88 prediction tests pass ruff/mypy/symvision clean epic-symbols empty; full check blocked only by pre-existing patch/stitch terminology defects recorded as follow-up

## Dependencies

- **Blocks:** [sase-1cj.12.4](sase-1cj.12.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.12.5](sase-1cj.12.5.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.2/README.md) | [sase-1cj.12.2](sase-1cj.12.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0256a9`](https://github.com/sase-org/sase/commit/e0256a98025b1b8119590e8b2e6e41856272aa11) | fix(tui): prompt prediction ghost, ranking gate, cache and archive fixes | [sase-1cj.12.2](sase-1cj.12.2.md) | 2026-09-29 18:51:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.12.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1cj.12.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.land/README.md

<!-- sase:referenced-by:end -->
