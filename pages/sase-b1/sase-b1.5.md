# Bead: sase-b1.5 — Render the swarm kind everywhere kinds are rendered

[Bead Pages](../README.md) / [sase-b1](README.md) / sase-b1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.5` · **Size:** small
**Created:** 2026-07-30 01:10:00 UTC · **Closed:** 2026-07-30 02:36:58 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

tui-labels: label the new kind in the Statistics XPrompts table and focus header, give it its own glyph and summary counting in the Agents-tab XPROMPTS panel, and document the attribution contract in the statistics help modal.

## Notes

[2026-07-30T02:36:58Z · sase-b1.5] tui-labels: added a shared _KIND_LABELS map in statistics_pane_xprompts.py so both _xprompt_cell and _xprompt_focus_header label kind 'swarm'; gave the Agents-tab XPROMPTS panel its own swarm glyph (❋) + color and swarm counting in _summary (swarm-only agents no longer summarize as '1 xprompt'); added a 'Swarms' row to the statistics help modal stating swarm origins are attributed to every agent the swarm launched and are forward-only (no backfill). statistics_pane_legends.py needs no change — its xprompts legend documents metrics, not kinds. Verified: new tests for a swarm table row, a swarm focus header, the swarm glyph/style/summary, and the help copy; targeted suites pass (46 passed). just lint exits 0; just test-visual for config_center_statistics passes 15/15 after refreshing config_center_statistics_help_120x40.png (diff confirmed to be only the scrollbar thumb shrinking from the added help row). Full 'just test' failure set is byte-identical to the pre-change baseline (69 pre-existing artifact-ref failures, this workspace is behind origin/master); 'just check' still fails only on the pre-existing SDD plan-link errors in the plans sidecar. Changes left uncommitted.

## Dependencies

- **Depends on:** [sase-b1.3](sase-b1.3.md) ✓
- **Depends on:** [sase-b1.4](sase-b1.4.md) ✓
- **Blocks:** [sase-b1.6](sase-b1.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.5/README.md) | [sase-b1.5](sase-b1.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e62f9a6`](https://github.com/sase-org/sase/commit/e62f9a6ee5bbe1072e517ca3adae4265e8479033) | feat(tui): render the swarm xprompt kind | [sase-b1.5](sase-b1.5.md) | 2026-07-30 02:38:07 |
