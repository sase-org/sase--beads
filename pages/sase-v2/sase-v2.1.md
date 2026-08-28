# Bead: sase-v2.1 — Stop the prompt panel double-render and cache its section anchors

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.1` · **Size:** medium
**Created:** 2026-08-28 09:01:19 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

section_visual: memoize prompt-panel section anchors per (generation, width) and stop SectionTrackingVisual.get_height from running a second full Rich console render on every measurement pass.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.1/README.md) | [sase-v2.1](sase-v2.1.md) | 0 |
