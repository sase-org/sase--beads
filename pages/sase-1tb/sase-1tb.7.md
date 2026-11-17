# Bead: sase-1tb.7 — Cell-preview fallback for terminals without kitty graphics

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.7` · **Size:** small
**Created:** 2026-11-17 11:16:34 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

non-kitty-fallback: detect kitty-graphics capability from the terminal name, using tmux's client_termname inside tmux. Otherwise render the current frame with the existing Unicode cell renderer plus metadata, and fall back the same way when kitten icat fails.

## Dependencies

- **Depends on:** [sase-1tb.6](sase-1tb.6.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.7/README.md) | [sase-1tb.7](sase-1tb.7.md) | 0 |
