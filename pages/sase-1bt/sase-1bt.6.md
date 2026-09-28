# Bead: sase-1bt.6 — Tools becomes a two-card deck with ⚒ Runs first

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.6` · **Size:** medium
**Created:** 2026-09-27 18:32:43 EDT · **Closed:** 2026-09-28 03:02:44 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

tools-deck-cards: give the Tools deck two card hosts (a ToolRunsDeckView card document and the unchanged LLM Calls panel), with per-card availability, the sticky default-card rule, a switcher status segment, active-card detail levels, availability for monitors and procs, and outcome-line run blocks.

## Notes

[2026-09-28T06:27:49Z · sase-1bt.6] PROPOSED FOLLOW-UP: test_files_ctrl_j_scrolls_page_anchor_to_top failed once under a loaded multi-file run and passed on isolated rerun — possible load flake, watch for repeats

[2026-09-28T07:02:15Z · sase-1bt.6--1] PROPOSED FOLLOW-UP: just check full-suite failures (29: agent_completion/directive_completion candidates, axe repeat_env inject, completion snapshot drift, timezone guard, top_bar/prompts_overlay etc.) reproduce identically on clean base tree (verified 6-test sample with changes stashed); triage verdict new_failures 26 NEW + 1 KNOWN (witness 555439a0d771d1302fbe2d199932645f) + 1 FLAKY — not caused by this phase

[2026-09-28T07:02:44Z · sase-1bt.6--1] Tools deck two-card phase done: ToolRunsDeckView card + unchanged LLM Calls panel, per-card availability, sticky default-card, switcher segment, detail levels, monitor/proc availability, outcome-line run blocks. Verified: new tests/ace/tui/test_tool_runs_deck_cards.py 29 passed; decks suite 547 passed; epic-symbols clean. Full just check 29 failures reproduce identically on clean base (6-test stashed sample), recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1bt.5](sase-1bt.5.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.7](sase-1bt.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bt.6.md) | [sase-1bt.6](sase-1bt.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`83dc078`](https://github.com/sase-org/sase/commit/83dc078e33c079009c5b78cd2abc54b8455941e8) | feat(ace-tui): give Tools deck two card hosts with Runs first (sase-1bt.6) | [sase-1bt.6](sase-1bt.6.md) | 2026-09-28 03:04:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.6--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bt.6.md

<!-- sase:referenced-by:end -->
