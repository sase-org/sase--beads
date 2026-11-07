# Bead: sase-1rq.4.1.2 — Fix the Ctrl-H/L word-motion undo test

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.2` · **Size:** small
**Created:** 2026-11-07 08:03:37 EST · **Closed:** 2026-11-07 09:32:47 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

word-motion: fix CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched (XCTAssertFalse at line 67: the undo manager can undo after Ctrl-L then Ctrl-H). It has failed on every CI run since edb2f48.

## Notes

[2026-11-07T13:23:39Z · sase-1rq.4.1.2] Cleared leftover panel-window undo in CaptureEditorWordMotionTests and disabled undo registration in moveByWord so Ctrl-H/L cannot leave an undo step. just portable-check passed on athena; scratch bundle.sh + typecheck-tests passed on mac. Unfiltered macos-ci-check staged as monitor vkv33r; follow-up judges the failed Swift tests list.

[2026-11-07T14:10:22Z · sase-1rq.4.1.2] Recovered the exact prior patch from snapshot af52c1d466d7a1b368852099e8424375f66fd0e6 onto unchanged origin/master 1e0a092. The current tracked tree is byte-identical to that snapshot (git diff af52c1d --exit-code passes). Unfiltered CI run 42376806344 passed lint/build and all six CaptureEditorWordMotionTests, including testMotionsLeaveTextAndUndoUntouched. It ran 4307 tests; remaining failures are the 11 known alias-lane tests and known intermittent testTripleEqualsGivesDoubleEquals. No failure outside the epic tables. Prior note records portable-check and mac bundle/typecheck success. The prior fix has not landed; this turn will declare it for host completion and monitor the landed master run before closing.

[2026-11-07T14:32:32Z · sase-1rq.4.1.2--1] PROPOSED FOLLOW-UP: Investigate relation-tilde forwarding failure on landed master — CI https://github.com/bobs-org/bob-mac-capture/actions/runs/42380490392 (job 128426881776, SHA 2a089e58087ceefdc93f6b3294bc87590d9b2bd9) failed CaptureSeparatorToggleTests.testRelationTildeOnlyForwardsAtBobReportedRelationEnd at CaptureSeparatorToggleTests.swift:497 (XCTAssertTrue, 2026-11-07T14:22:11Z). This test is outside the epic failure tables; the other 11 failed test cases are the known alias-lane failures. The full suite completed 4307 tests with 1 skipped and 28 assertion failures; there was no watchdog timeout. All six CaptureEditorWordMotionTests passed, as did testTripleEqualsGivesDoubleEquals. The landed tracked tree is byte-identical to unfiltered snapshot af52c1d466d7a1b368852099e8424375f66fd0e6 (run 42376806344), whose prior recorded failure list did not include the relation-tilde test. Leave classification and any repair to the flakes/master-green phases; no task bead created.

[2026-11-07T14:32:47Z · sase-1rq.4.1.2--1] Verified the fix landed on master as 2a089e58087ceefdc93f6b3294bc87590d9b2bd9 and the entire tracked tree matches unfiltered snapshot af52c1d466d7a1b368852099e8424375f66fd0e6 (git diff --exit-code passed). Snapshot CI https://github.com/bobs-org/bob-mac-capture/actions/runs/42376806344 passed lint/build and all six CaptureEditorWordMotionTests, as recorded in note 2. Inspected the full exact-SHA master CI Test log at https://github.com/bobs-org/bob-mac-capture/actions/runs/42380490392/job/128426881776: lint/build passed and all six CaptureEditorWordMotionTests passed with 0 failures, including testMotionsLeaveTextAndUndoUntouched at 14:18:38Z. Prior note records portable-check and scratch mac bundle/typecheck success. Overall master CI remains red on 11 known alias-lane tests plus the relation-tilde failure recorded in the PROPOSED FOLLOW-UP note; those are outside this phase. sase bead epic-symbols reported no entries for sase-1rq.4.1.2. Closed only this assigned phase; no ancestors closed.

## Dependencies

- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.2.md) | [sase-1rq.4.1.2](sase-1rq.4.1.2.md) | 0 |
