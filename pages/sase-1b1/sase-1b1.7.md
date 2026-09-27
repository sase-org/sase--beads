# Bead: sase-1b1.7 — User docs for deck views

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.7` · **Size:** small
**Created:** 2026-09-27 05:45:24 EDT · **Closed:** 2026-09-27 12:47:14 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

docs: document deck views, the badge legend, P, palette reset, persistence, and the Auto-only scope of the spread thresholds in docs/ace.md and docs/configuration.md. Record a proposed glossary follow-up.

## Notes

[2026-09-27T10:08:58Z · 0t2] CROSS-EPIC (sase-1b2): sase-1b2.20 edits the same `docs/ace.md` sections (Agent Data Decks and Cards, Card Blocks, Deck Picker, key tables) and the `ace.agent_decks` part of `docs/configuration.md`. Describe only shipped behavior. If the FINAL deck has shipped (sase-1b2.19 closed), say that deck views apply to Main and Files only, that FINAL (like Tools) always pages automatically with no badge, and that `P` is unavailable there. Your PROPOSED FOLLOW-UP for a "Deck View" glossary strand should say the same, and it should agree with sase-1b2.20's proposed agent-data-deck strand edit, which lists FINAL among the decks. The full shared rules are in the NOTES on epic sase-1b1.

[2026-09-27T15:48:48Z · sase-1b1.7] PROPOSED FOLLOW-UP: add a "Deck View" glossary strand defining spread / page cards / page blocks views, the auto-vs-fixed policy, the P cycle, and that views are per-panel per-deck (Main and Files; Tools always pages automatically with no badge)

[2026-09-27T16:46:57Z · sase-1b1.7--1] PROPOSED FOLLOW-UP: symvision reports 4 unused public symbols (run_view_step_from_dict, run_view_appearance_from_dict, RunViewRecoveryTurn in src/sase/core/finalizer_run_view.py; run_duration_seconds in src/sase/ace/tui/widgets/decks/final/run_blocks.py) plus 52 known; reproduces identically on clean base tree with docs stashed, unrelated to this docs-only phase

[2026-09-27T16:47:14Z · sase-1b1.7--1] Docs-only phase: deck views, P cycle, palette, persistence, and Auto-only spread thresholds documented in docs/ace.md and docs/configuration.md. just check symvision failure (4 unused symbols) reproduces identically on clean base tree; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1b1.5](sase-1b1.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.7.md) | [sase-1b1.7](sase-1b1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c6d68d8`](https://github.com/sase-org/sase/commit/c6d68d861ec77d490d160aa859b31fc689614858) | docs(deck-views): document deck views, P cycle, palette, persistence (sase-1b1.7) | [sase-1b1.7](sase-1b1.7.md) | 2026-09-27 12:59:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |
| read-by | [agent:sase-1b1.7--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.7.md

<!-- sase:referenced-by:end -->
