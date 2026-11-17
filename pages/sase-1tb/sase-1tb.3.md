# Bead: sase-1tb.3 — Move tmux split and decoration off the Textual UI thread

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.3` · **Size:** medium
**Created:** 2026-11-17 11:16:33 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

async-pane-launch: launch the tmux split and pane decoration in a pump-free worker with an explicit launch context and bounded tmux timeouts. Show an opening state, show a VCS-materialization progress toast, and emit parent-side open spans correlated with the child.

## Dependencies

- **Depends on:** [sase-1tb.2](sase-1tb.2.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.3/README.md) | [sase-1tb.3](sase-1tb.3.md) | 0 |
