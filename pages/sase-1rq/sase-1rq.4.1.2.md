# Bead: sase-1rq.4.1.2 — Fix the Ctrl-H/L word-motion undo test

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.2` · **Size:** small
**Created:** 2026-11-07 08:03:37 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

word-motion: fix CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched (XCTAssertFalse at line 67: the undo manager can undo after Ctrl-L then Ctrl-H). It has failed on every CI run since edb2f48.

## Dependencies

- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.2.md) | [sase-1rq.4.1.2](sase-1rq.4.1.2.md) | 0 |
