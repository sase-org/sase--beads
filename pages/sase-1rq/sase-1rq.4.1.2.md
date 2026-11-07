# Bead: sase-1rq.4.1.2 — Fix the Ctrl-H/L word-motion undo test

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.2` · **Size:** small
**Created:** 2026-11-07 08:03:37 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

word-motion: fix CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched (XCTAssertFalse at line 67: the undo manager can undo after Ctrl-L then Ctrl-H). It has failed on every CI run since edb2f48.

## Notes

[2026-11-07T13:23:39Z · sase-1rq.4.1.2] Cleared leftover panel-window undo in CaptureEditorWordMotionTests and disabled undo registration in moveByWord so Ctrl-H/L cannot leave an undo step. just portable-check passed on athena; scratch bundle.sh + typecheck-tests passed on mac. Unfiltered macos-ci-check staged as monitor vkv33r; follow-up judges the failed Swift tests list.

## Dependencies

- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.2.md) | [sase-1rq.4.1.2](sase-1rq.4.1.2.md) | 0 |
