# Bead: sase-bg.4 — ACE TUI task surfaces and PNG goldens

[Bead Pages](../README.md) / [sase-bg](README.md) / sase-bg.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bg.4` · **Size:** large
**Created:** 2026-07-30 22:55:33 UTC · **Closed:** 2026-07-31 01:14:15 UTC
**Plan:** [202607/task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202607/task_beads.md)

## Description

tui: add a Tasks section and task row kind to the Plans pane with filters and detail chips, make the agents-pane bead lane and plan-association role type-aware, extend the bead autocomplete and edit modal, and regenerate PNG snapshot goldens with open and ready task fixtures.

## Notes

[2026-07-31T01:14:15Z · sase-bg.4] Implemented approved TUI task surfaces; verified 24,623 passed and 7 skipped, visual suite 392 passed and 1 skipped, formatting, Ruff, mypy, Symvision, size checks, committed-plan validation, and git diff --check. Aggregate just check remains blocked only by unrelated external SASE validation drift in chezmoi and another July plan.

## Dependencies

- **Blocks:** [sase-bg.10](sase-bg.10.md) ✓
- **Depends on:** [sase-bg.3](sase-bg.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bg.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-bg.4.md) | [sase-bg.4](sase-bg.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f592b43`](https://github.com/sase-org/sase/commit/f592b43dfe5d0c6e1e68ab1e71c2124f6d013d2a) | feat(tui): surface task beads in ACE | [sase-bg.4](sase-bg.4.md) | 2026-07-31 01:15:10 |
