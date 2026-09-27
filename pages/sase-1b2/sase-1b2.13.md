# Bead: sase-1b2.13 — Read-only sase final status run view

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.13` · **Size:** small
**Created:** 2026-09-27 05:49:46 EDT · **Closed:** 2026-09-27 09:15:39 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-cli-status: add `sase final status [<agent>]` with -d/--artifacts-dir and -f/--format pretty|json over the shared collector and projection. It prints colored output in the shared vocabulary, keeps help alphabetical, and defaults to the calling agent inside a SASE turn.

## Notes

[2026-09-27T13:10:56Z · sase-1b2.13--1] PROPOSED FOLLOW-UP: mypy _tree.py:622 prefix_key no-redef + :623/:629 GroupKey arg-type reproduce on clean base (file untouched by this phase); already tracked by sase-1b2.7 notes

[2026-09-27T13:15:39Z · sase-1b2.13--2] final-cli-status done: sase final status pretty|json over shared collector verified; ruff format clean (10406 files), mypy clean on src/sase/finalizers/cli.py + final_handler.py + parser_final.py, pytest tests/test_final_status_command.py 9 passed, epic-symbols empty; remaining just-check mypy _tree.py:622/623/629 pre-existing on clean base tracked by sase-1b2.7 + PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-1b2.12](sase-1b2.12.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.19](sase-1b2.19.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.13.md) | [sase-1b2.13](sase-1b2.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0b25ee`](https://github.com/sase-org/sase/commit/a0b25eea567fe4941be3476d14d647a317d1ea25) | feat(final): add read-only sase final status run view | [sase-1b2.13](sase-1b2.13.md) | 2026-09-27 09:17:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.13--2][2] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.13.md

<!-- sase:referenced-by:end -->
