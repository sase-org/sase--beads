# Bead: sase-1bn.3 — Paint-time rail projection inside AgentList

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.3` · **Size:** medium
**Created:** 2026-09-27 17:33:16 EDT · **Closed:** 2026-09-27 19:17:31 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

rail-projection: give AgentList a set_rail() render mode that overrides _get_visual with a cache validated by prompt identity. Record an all-banner _group_at_row map, add a rows-changed hook to every structural path (fixing the insert path's ordering), and paint the overflow subtitle. Add unit and guard tests, still unwired.

## Notes

[2026-09-27T23:16:44Z · sase-1bn.3] PROPOSED FOLLOW-UP: symvision gate is red on the clean base tree (unused public symbols across ~55 files untouched by sase-1bn.3, including dead _run privates in src/sase/scripts/sase_chop_*.py plus rail_panel_title/rail_tooltip_text/rail_urgency awaiting rail-wiring/mode-affordances; zero overlap with the 1bn.3 diff, which strictly removes 3 unused findings) — triage into a task bead or leave for the epic land agent

[2026-09-27T23:17:31Z · sase-1bn.3] Rail projection done and verified: set_rail toggles without rebuild (same Options, highlight, scroll, option._visual untouched); every rail row is 1 line with 6 content cells; patch_row repaints glyph via prompt-identity cache; insert/remove keep shifted cells; folds authoritative with identical row counts; overflow subtitle tracks scrolling; Textual hook guard test locks _get_visual routing. 8 new tests pass, 515 agent-list + 497 deck tests pass, ruff/mypy clean, symvision shows zero findings in this diff (full-gate red is pre-existing, recorded as follow-up).

## Dependencies

- **Depends on:** [sase-1bn.2](sase-1bn.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bn.5](sase-1bn.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.3/README.md) | [sase-1bn.3](sase-1bn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f4cfc51`](https://github.com/sase-org/sase/commit/f4cfc51d701a1a459642b12870471a2d4a8d33a0) | feat(ace-tui): paint-time node rail projection inside AgentList (sase-1bn.3) | [sase-1bn.3](sase-1bn.3.md) | 2026-09-27 19:20:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bn.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.3/README.md

<!-- sase:referenced-by:end -->
