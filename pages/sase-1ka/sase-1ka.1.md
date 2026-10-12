# Bead: sase-1ka.1 — Decision cards replace the Button accordion

[Bead Pages](../README.md) / [sase-1ka](README.md) / sase-1ka.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4a.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4a.linker.w0.md) · **Assignee:** `sase-1ka.1` · **Size:** medium
**Created:** 2026-10-12 09:11:08 EDT · **Closed:** 2026-10-12 09:57:10 EDT
**Plan:** [202610/gate\_panel\_decision\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202610/gate_panel_decision_cards.md)

## Description

cards: replace each decision Button with a wrapping DecisionCard built from pure Rich card builders, make the decisions rail a plain Vertical whose list fills to the Verdict, add the focus bar, answer chips, new header copy, mouse selection, once-per-keypress sheet computation, the syncthing and max-copy fixtures, the no-clip pilot invariant, and the regenerated decision goldens.

## Notes

[2026-10-12T13:56:08Z · sase-1ka.1] PROPOSED FOLLOW-UP: stale --epic-symbol sase-1jx.11(NewProjectModal) in Justfile line 449 fails symvision on clean base (bead closed); needs removal by sase-1jx land agent -r recording pre-existing check failure found during phase verification

[2026-10-12T13:57:10Z · sase-1ka.1] Cards phase done: pure builders (plan_decision_cards.py), DecisionCard+slots widget, plain-Vertical rail, chips/focus bar/new header copy, mouse select, sheet-once-per-keypress with selective re-render; syncthing+maxcopy fixtures; no-clip pilot invariant (old Buttons clipped 59 cells); 8 goldens regenerated+inspected; 78 decision tests green, ruff+mypy clean; only check failure is pre-existing sase-1jx.11 stale epic-symbol (recorded as follow-up)

## Dependencies

- **Blocks:** [sase-1ka.2](sase-1ka.2.md) ◐ · ⧖ 2026-10-12
- **Blocks:** [sase-1ka.4](sase-1ka.4.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ka.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ka.1/README.md) | [sase-1ka.1](sase-1ka.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`648ef1a`](https://github.com/sase-org/sase/commit/648ef1a390114436de898552144ada0d18497799) | feat(ace): replace Button accordion with decision cards in plan approval modal | [sase-1ka.1](sase-1ka.1.md) | 2026-10-12 09:58:56 EDT |
