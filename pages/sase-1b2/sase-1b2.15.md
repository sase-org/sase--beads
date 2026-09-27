# Bead: sase-1b2.15 — The Overview card

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.15

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.15` · **Size:** small
**Created:** 2026-09-27 05:49:48 EDT · **Closed:** 2026-09-27 10:34:33 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-overview-card: render the run-level Overview card. It shows the plan in DAG order with selection reasons, configured-but-unselected instances dimmed, the declaration timeline, controller cycles only when above one, drift, run-level diagnostics, the runs ledger, calm skipped/not-reached/unavailable states and CLI pointers.

## Notes

[2026-09-27T14:23:42Z · sase-1b2.15--1] PROPOSED FOLLOW-UP: whole-repo _lint-symvision red on 53 pre-existing unused-public symbols (RunView* family, view_policy, status_summary, steps, progress, operation_records, etc.); verified identical set on clean HEAD worktree /tmp/sase_base; possibly overlapping task bead sase-1ay (13 symbols) — needs triage/expansion

[2026-09-27T14:34:07Z · sase-1b2.15--1] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_card_document_view.py::test_card_document_decks_is_main_only fails on clean HEAD too — asserts CARD_DOCUMENT_DECKS==(MAIN,) but phase sase-1b2.14 registered (MAIN, FINAL); needs test update by a later phase or the deck owner

[2026-09-27T14:34:33Z · sase-1b2.15--1] Overview card done: render_overview_lines wired into final document with DAG plan rows, declaration timeline, controller/drift/diagnostics/runs ledger, calm states and CLI pointers; 18 overview tests pass; fmt/ruff/mypy and all other check gates green; fixed my 2 symvision-owned symbols by privatizing (test import updated); remaining 53 symvision unused-publics and 1 neighboring deck test failure both reproduce identically on clean HEAD — recorded as PROPOSED FOLLOW-UP (see sase-1ay)

## Dependencies

- **Depends on:** [sase-1b2.14](sase-1b2.14.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.17](sase-1b2.17.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.15](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.15.md) | [sase-1b2.15](sase-1b2.15.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e75840b`](https://github.com/sase-org/sase/commit/e75840b0c9f665a7b22b6bbd2a107f17e63df89d) | feat(final-deck): add Overview card widget with document deck and tests | [sase-1b2.15](sase-1b2.15.md) | 2026-09-27 10:46:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.15--1][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1b2.16][3] | sibling overview card scope to avoid overlap | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.15.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.16/README.md

<!-- sase:referenced-by:end -->
