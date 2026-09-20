# Bead: sase-142.2 — Stop collapsed panels forcing a full rebuild on every apply

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-13i.4.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-13i.4.f0.f0.md) · **Assignee:** `sase-142.2` · **Size:** small
**Created:** 2026-09-20 12:14:21 EDT · **Closed:** 2026-09-20 12:40:29 EDT
**Plan:** [202609/epic\_panel\_new\_node\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_panel_new_node_flicker.md)

## Description

collapsed-panel-mode: record the active grouping mode when a panel paints collapsed so the stale_grouping_mode guard stops sending 232 of 234 applies down the full-rebuild path, without weakening the guard for panels that hold rows from an earlier mode.

## Notes

[2026-09-20T16:40:29Z · sase-142.2] render_collapsed(*, grouping_mode) now records the mode a collapsed panel painted under (no default; both callers pass it). The 3-panel BY_STATUS probe with one collapsed panel now reports the guard True and no stale_grouping_mode fallback or full rebuild on changed or unchanged applies. The guard is untouched: BY_STATUS->STANDARD with a collapsed panel still fails it. New tests in test_agent_display_collapsed_panel_mode.py: 6 of 7 fail on the old tree; the 7th, the grouping-cycle guard test, passes on both. just test-scoped: 43806 passed, 4 failed, and the same 4 fail on clean HEAD (lazy_tier2_reconcile_apply, 2x capacity_gate_to_admission, contract_manifest). just check stops at symvision unused-public-symbol failures in files this change doesn't touch (not verified on clean HEAD).

## Dependencies

- **Blocks:** [sase-142.3](sase-142.3.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-142.4](sase-142.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.2/README.md) | [sase-142.2](sase-142.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`686851c`](https://github.com/sase-org/sase/commit/686851c9e3db8c489e4e4259c7411bed07e6a5f4) | fix(tui): record grouping mode on collapsed panels so applies stay incremental | [sase-142.2](sase-142.2.md) | 2026-09-20 12:41:35 EDT |
