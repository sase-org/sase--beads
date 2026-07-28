# Bead: sase-t.1 — Phase 1 — Foundation: grouping mode model & key functions

[Bead Pages](../README.md) / [sase-t](README.md) / sase-t.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-t.1`
**Created:** 2026-04-26 05:13:00 UTC · **Closed:** 2026-04-26 05:28:37 UTC
**Plan:** [202604/agents\_tab\_grouping\_modes.md](https://github.com/sase-org/sase--plans/blob/main/202604/agents_tab_grouping_modes.md)

## Description

Pure-data layer. Introduce GroupingMode enum and helpers in src/sase/ace/tui/models/agent_groups.py. Generalize _grouping_keys_for, _panel_uses_changespec_level, and build_agent_tree to accept GroupingMode. No TUI/keymap/rendering changes. Unit tests for date bucketing, status mapping, and tree shape per mode.

## Notes

COMMIT: 330528ae

## Dependencies

- **Blocks:** [sase-t.2](sase-t.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ec7f078`](https://github.com/sase-org/sase/commit/ec7f078d2261355c0b800e5acba9f13e97107493) | feat: add GroupingMode model + date/status bucket helpers (Phase 1) (sase-t.1) | [sase-t.1](sase-t.1.md) | 2026-04-26 05:28:41 |
