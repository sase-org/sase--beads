# Bead: sase-v2.1 — Stop the prompt panel double-render and cache its section anchors

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.1` · **Size:** medium
**Created:** 2026-08-28 09:01:19 EDT · **Closed:** 2026-08-28 09:47:50 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

section_visual: memoize prompt-panel section anchors per (generation, width) and stop SectionTrackingVisual.get_height from running a second full Rich console render on every measurement pass.

## Notes

[2026-08-28T13:47:50Z · sase-v2.1] Implemented cached AgentPromptPanel SectionTrackingVisual reuse and per-generation/width section-anchor memoization; verified focused prompt-panel section-navigation tests, section rendering/fold-adjacent tests, and just check.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.1/README.md) | [sase-v2.1](sase-v2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1858f75`](https://github.com/sase-org/sase/commit/1858f75606b82b31087410dc5447ccfcf731759c) | fix(tui): cache prompt panel section visuals | [sase-v2.1](sase-v2.1.md) | 2026-08-28 09:49:43 EDT |
