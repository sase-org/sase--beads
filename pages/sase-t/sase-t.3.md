# Bead: sase-t.3 — Phase 3 — Keymap, cycle action, per-mode fold state

[Bead Pages](../README.md) / [sase-t](README.md) / sase-t.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-t.3`
**Created:** 2026-04-26 05:13:10 UTC · **Closed:** 2026-04-26 06:00:31 UTC
**Plan:** [202604/agents\_tab\_grouping\_modes.md](https://github.com/sase-org/sase--plans/blob/main/202604/agents_tab_grouping_modes.md)

## Description

User-facing interactivity. Add cycle_grouping_mode: 'g' to default_config.yml. Add action_cycle_grouping_mode on agents-tab actions mixin (likely new file _grouping.py). Per-mode fold registry dict[GroupingMode, GroupFoldRegistry]. Initialize in actions/startup.py. Update _loading.py and _folding.py callers. Tests for cycle order, fold state preservation across modes, and tree shape after cycling.

## Notes

COMMIT: 7c6e289b

## Dependencies

- **Depends on:** [sase-t.2](sase-t.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`2fb1d77`](https://github.com/sase-org/sase/commit/2fb1d7701699eaea531bee2552c7d5a893bf0120) | feat: cycle Agents-tab grouping mode with \`g\` (Phase 3, sase-t.3) (sase-t.3) | [sase-t.3](sase-t.3.md) | 2026-04-26 06:00:35 |
