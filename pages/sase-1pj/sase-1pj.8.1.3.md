# Bead: sase-1pj.8.1.3 — Make agent monitor starts stage unconditionally

[Bead Pages](../README.md) / [sase-1pj.8.1](sase-1pj.8.1.md) / sase-1pj.8.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.3` · **Size:** medium
**Created:** 2026-11-02 20:59:31 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

## Description

monitor-staging: remove the agent monitor kill branch and print-before-kill workarounds while preserving prepared completion, ToolRun joins, replay, and outside-agent starts.

## Notes

[2026-11-03T02:48:52Z · sase-1pj.8.1.3--1] Verified: in-agent monitor starts stage unconditionally; kill branch, print-before-kill workarounds, and dead write_handoff_inflight_marker removed; just _lint-symvision clean; focused monitor-staging tests passed (67); no leftover --epic-symbol entries. Full just check handed to prepared host-completion monitor.

## Dependencies

- **Blocks:** [sase-1pj.8.1.4](sase-1pj.8.1.4.md) ◐ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.1.3.md) | [sase-1pj.8.1.3](sase-1pj.8.1.3.md) | 0 |
