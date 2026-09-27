# Bead: sase-1bn.1 — Three sidebar modes and the zoom state fixes

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.1` · **Size:** medium
**Created:** 2026-09-27 17:33:12 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

sidebar-modes: derive EXPANDED / RAIL / HIDDEN from deck-area state. Stop zoom from writing nodes_collapsed, and make Ctrl+S while zoomed restore the snapshot like Z. Route every deck-state change through one sync choke point, un-nest the info-row zoom chip, and update the tests, docs, and zoom goldens.

## Dependencies

- **Blocks:** [sase-1bn.4](sase-1bn.4.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bn.5](sase-1bn.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.1.md) | [sase-1bn.1](sase-1bn.1.md) | 0 |
