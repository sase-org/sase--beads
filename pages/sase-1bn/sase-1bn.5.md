# Bead: sase-1bn.5 — Wire the rail into the Agents tab and delete NodeSpine

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.5` · **Size:** medium
**Created:** 2026-09-27 17:33:20 EDT · **Closed:** 2026-09-27 21:26:08 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

rail-wiring: RAIL mode shows the tribe lists in rail form at a fixed width. Focus stays on the list, titles and newly mounted panels become rail-aware, and runtime ticks pause with a catch-up on expand. The info-row nodes chip becomes clickable, and NodeSpine, its handler, CSS, and tests are deleted. Includes pilot tests and rail goldens.

## Notes

[2026-09-28T01:25:19Z · sase-1bn.5] PROPOSED FOLLOW-UP: first Ctrl+S after fold plus programmatic refreshes is intermittently swallowed before deck state changes (focus/Screen/tab all correct, no modal); golden rail entry uses bounded retry, needs root-cause investigation

[2026-09-28T01:26:08Z · sase-1bn.5] Rail wired into Agents tab, NodeSpine deleted. Verified: 9 pilot wiring tests + 53 rail/collapse unit tests + 93 panel title/focus tests + 562 deck/info-panel tests pass; ruff/fmt/mypy/symvision clean for touched files; 8/8 PNG goldens check-clean (5 new node-rail goldens with SVG-census judgment: ?/X fail, run/done, monitor, gate, folded banner, unclipped 5-cell titles, overflow subtitle; 3 collapsed/split goldens regenerated without spine). Full sase tool run check blocked by shared Rust rebuild lock (another workspace building sase-core); test_slow_retrying_finalizer failure is that stale 0.35.0 extension missing project_finalizer_node_view, unrelated to this diff.

## Dependencies

- **Depends on:** [sase-1bn.1](sase-1bn.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bn.3](sase-1bn.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bn.7](sase-1bn.7.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.5/README.md) | [sase-1bn.5](sase-1bn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f03e50`](https://github.com/sase-org/sase/commit/2f03e5059b09cbefab5abce55bc94441a9f2fc98) | feat(ace-tui): project tribe lists at fixed 9-cell rail width | [sase-1bn.5](sase-1bn.5.md) | 2026-09-27 21:29:59 EDT |
