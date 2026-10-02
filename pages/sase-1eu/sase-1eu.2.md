# Bead: sase-1eu.2 — Shared pure PaneGrid model and golden transition table

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.2` · **Size:** medium
**Created:** 2026-10-02 11:33:52 EDT · **Closed:** 2026-10-02 12:44:51 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

pane-grid-model: add a stdlib-only PaneGrid algebra (split key rule, close, focus ring, swap, turn, resize, MRU target, fit, positions, grid spec). Pin it with a golden transition table, Hypothesis invariants, and an import-weight test.

## Notes

[2026-10-02T16:44:32Z · sase-1eu.2--1] PROPOSED FOLLOW-UP: just check test-scoped lane has 6 KNOWN failures unrelated to pane-grid change (triage verdict no_new_failures, ToolRun 389b3cd1f5fc81fa58809ff87184dfff): test_app_import_budget tracked by sase-13p (sase-13r closed as its duplicate; no src file imports pane_grid so new module cannot affect startup import count), test_deck_block_spread_pilot tracked by sase-1bl, 3x directive-completion + xprompt-directive-contract nodes have triage witnesses 1be65fad22d344811fc863e9abe904ea / 1882e81178a97bf5c5bf7e463a4aaeb4 with no owning task bead yet — land agent may file or +1 as appropriate.

[2026-10-02T16:44:51Z · sase-1eu.2--1] PaneGrid model delivered and verified: new src/sase/ace/tui/util/pane_grid.py (stdlib-only split/close/focus-ring/swap/turn/resize/MRU/fit/positions/grid-spec algebra, zero src importers); golden transition table 17 states x 10 keys + nest-off table pass; 9 Hypothesis invariants pass; import-cost test passes (20/20 in tests/ace/tui/util/test_pane_grid*.py); ruff/mypy/symvision/keep-sorted green in-run; sase bead epic-symbols sase-1eu.2 clean (0 phase entries, 20 symbols re-keyed to open parent epic sase-1eu). just check test-scoped lane: 51574 passed, 6 KNOWN failures triaged no_new_failures and recorded as PROPOSED FOLLOW-UP (sase-13p, sase-1bl, triage witnesses).

## Dependencies

- **Blocks:** [sase-1eu.3](sase-1eu.3.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.6](sase-1eu.6.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.2.md) | [sase-1eu.2](sase-1eu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fc8830c`](https://github.com/sase-org/sase/commit/fc8830c6bcae33187028c36075086347dfc44653) | feat(ace): add shared pure PaneGrid model with golden transition table | [sase-1eu.2](sase-1eu.2.md) | 2026-10-02 12:48:23 EDT |
