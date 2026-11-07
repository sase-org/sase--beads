# Bead: sase-1rq.4.1.1 — Fix the eleven sigil-alias rewrite-lane tests that have never passed on CI

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.1` · **Size:** large
**Created:** 2026-11-07 08:03:37 EST · **Closed:** 2026-11-07 12:47:47 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

alias-lane: fix the 11 deterministic CaptureSeparatorToggleTests / CapturePanelModelTests sigil-alias failures (`.`, `;`, `,`, `\`, `/` aliases) that fail on every macOS 26 CI run. Find the shared root cause in the Swift rewrite lane or the test harness, fix it, and prove it with Scripts/macos-ci-check before landing.

## Notes

[2026-11-07T13:13:50Z · sase-1rq.4.1.1] Planning investigation at master 1e0a092441d0a2bc0a50fc5c42ec09fd7463ce89: no prior implementation or later fix is present. Run 42337582432/job 128297901212 confirms period/move/next-parent rewritten-text assertions pass; subsequent picker waits fail. Direct fake-bob calls reproduce missing parse needs/spans for @file^, both short move-bullet drafts, @cash+goog-exit +, and lowercase Call bank @ca/@cash. Hash task-type tests omit FAKE_BOB_TASK_TYPE_CHOOSER=1. Routed comma completion is shadowed by an earlier legacy fake branch; comma tests also lack native apply wiring, assert asynchronous output synchronously, and inspect inline completion rather than the parent picker. Prepared a validated medium tale plan covering faithful fixture responses, editor wiring, picker assertions, compilation, and unfiltered snapshot plus exact-SHA master verification. No implementation files changed; bead remains in progress for the approved coder.

[2026-11-07T14:14:40Z · sase-1rq.4.1.1--1] Unfiltered macos-ci-check run 42378175085 (https://github.com/bobs-org/bob-mac-capture/actions/runs/42378175085), snapshot SHA f71df3f86d99ff792ca1a597fe5db8c5596ab26d, job 128419997267. Exit 1. Tool run dadad5c24cf44c8a08c6b57bf3c7f410, monitor ee032d1kch6e.

Eleven alias-lane tests:
- CaptureSeparatorToggleTests.testPeriodAliasAfterRouteOpensNewIDBlockPicker PASSED (0.172s)
- CaptureSeparatorToggleTests.testNativeUndoRestoresLiteralSigilAliasWithoutRetriggering FAILED at line 1078 waitUntil !pickerVisible (5.284s). First waitUntil for rewritten `@file^` + picker now succeeds; master 42337582432 timed out at that first wait.
- CaptureSeparatorToggleTests.testDelayedAcceptedAliasSupersedesGatedCompletion PASSED (0.525s)
- CaptureSeparatorToggleTests.testPeriodAliasOnMoveBulletOpensMovePicker PASSED (0.199s)
- CaptureSeparatorToggleTests.testSemicolonAliasOnOfferMoveBulletOpensMoveAndLinkPicker PASSED (0.165s)
- CaptureSeparatorToggleTests.testUndoAfterMoveAliasRestoresLiteralWithoutRetriggering FAILED at line 1177 waitUntil !pickerVisible (5.383s). Same pattern: rewrite+picker now succeed; master timed out at the first wait.
- CaptureSeparatorToggleTests.testCommaAfterCompleteTargetRunOpensNextParentPicker PASSED (0.302s)
- CaptureSeparatorToggleTests.testBackslashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.534s)
- CaptureSeparatorToggleTests.testSlashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.575s)
- CapturePanelModelTests.testCommaOnExactRouteUsesBobRewriteLane PASSED (0.194s)
- CapturePanelModelTests.testCommaCommitsPartialRouteThenBobOpensParentTaskPicker PASSED (0.346s)

Sibling/unrelated:
- CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched FAILED XCTAssertFalse at line 67 — same as master 42337582432 (word-motion phase).
- CaptureSeparatorToggleTests.testSemicolonAliasAfterRouteOpensLinkModeBlockPicker FAILED waitUntil pickerVisible (5.054s). This test PASSED (0.091s) on master 42337582432. testCompletionWaitsForRewriteThenOpensPicker (direct `:`) PASSED (0.598s) on this snapshot. Not quarantining; will re-check after the undo picker-dismiss fix.

Product bug: after a successful alias rewrite the picker opens, then native undo restores the literal (`.` / move-bullet `.`) and editorTextDidChange runs, but handleMissingCompletion / applyNonActiveTaskCompletion keep an open picker when picker.draftSnapshot no longer matches the editor. closePickerAfterStaleDraft already exists for picker actions. Wiring it from editorTextDidChange, next to the task-ID / Pomodoro prompt snapshot checks.

[2026-11-07T15:01:06Z · sase-1rq.4.1.1--2] Unfiltered macos-ci-check run 42381542095 (https://github.com/bobs-org/bob-mac-capture/actions/runs/42381542095), snapshot SHA 4a2257c60e2a0055723ad4f04dc266d392b6a696, job 128430011909. Exit 1. Tool run bc1b94a7bfc5b349b23c48cd35864da9, monitor fsfgpawsw5jc.

Eleven alias-lane tests (all PASSED):
- CaptureSeparatorToggleTests.testPeriodAliasAfterRouteOpensNewIDBlockPicker PASSED (0.201s)
- CaptureSeparatorToggleTests.testNativeUndoRestoresLiteralSigilAliasWithoutRetriggering PASSED (0.119s)
- CaptureSeparatorToggleTests.testDelayedAcceptedAliasSupersedesGatedCompletion PASSED (0.476s)
- CaptureSeparatorToggleTests.testPeriodAliasOnMoveBulletOpensMovePicker PASSED (0.244s)
- CaptureSeparatorToggleTests.testSemicolonAliasOnOfferMoveBulletOpensMoveAndLinkPicker PASSED (0.331s)
- CaptureSeparatorToggleTests.testUndoAfterMoveAliasRestoresLiteralWithoutRetriggering PASSED (0.234s)
- CaptureSeparatorToggleTests.testCommaAfterCompleteTargetRunOpensNextParentPicker PASSED (0.271s)
- CaptureSeparatorToggleTests.testBackslashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.420s)
- CaptureSeparatorToggleTests.testSlashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.456s)
- CapturePanelModelTests.testCommaOnExactRouteUsesBobRewriteLane PASSED (0.284s)
- CapturePanelModelTests.testCommaCommitsPartialRouteThenBobOpensParentTaskPicker PASSED (0.504s)

Previously failing semicolon test now PASSED:
- CaptureSeparatorToggleTests.testSemicolonAliasAfterRouteOpensLinkModeBlockPicker PASSED (0.127s) (failed 5.054s on snapshot 42378175085; passed 0.091s on master 42337582432)

Sibling/unrelated:
- CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched FAILED XCTAssertFalse line 67 — same as master 42337582432 (word-motion phase).

New failures caused by the blanket editorTextDidChange closePickerAfterStaleDraft (all PASSED on master 42337582432 and snapshot 42378175085):
- CaptureRelatedLaneTests.testNoSpawnWhileModalOwnsPanel FAILED: spawn count 2 vs 1 and draft "Install new UPS battery plus cable" vs held "Install new UPS battery". Typing while a dependency picker owns the panel closed the picker, so similar-tasks respawned.
- CaptureRelationEqualsAliasTests.testEqualsAliasOpensLinksToAndCallsRewriteBeforeCompletion FAILED 10.327s waitUntil picker+rewritten `Fix it ~` (passed 0.288s master / 0.282s prior snapshot). closePickerAfterStaleDraft also clears equalsGestureArm.
- CaptureRelationEqualsAliasTests.testTildeFlipFastEqualsAfterPickerRestoresTildeEquals FAILED 10.209s waitUntil `New task ~~` + picker .linkedFrom. Sibling testTildeFlipThenFastEqualsRestoresTildeEquals (text only, no picker wait) PASSED 0.206s, so the rewrite landed and the picker did not stay.
- CaptureRelationEqualsAliasTests.testTripleEqualsGivesDoubleEquals FAILED 10.293s at openTimestampedAlias waitUntil. testFastSecondEqualsUndoesOpenerAfterReply and testSlowSecondEqualsFlipsAfterReply use the same helper and PASSED.

Product fix: do not close every stale picker from editorTextDidChange. Dismiss only `.blockID` and `.projectTaskMove` sessions after the rewrite-echo early return, which is what the two undo tests wait on. Leave modal dependency pickers and relation/`=` pickers in place.

[2026-11-07T15:32:32Z · sase-1rq.4.1.1--3] Unfiltered macos-ci-check run 42384626815 (https://github.com/bobs-org/bob-mac-capture/actions/runs/42384626815), snapshot SHA b216fe29b4cbf7d3a92e33441ae79c983af2726f, job 128439305860. Exit 1. Tool run 7517167b664d0c5ef1aaca7b3e223a83, monitor 7qcgd9vs6wgb. Base SHA 1e0a092441d0a2bc0a50fc5c42ec09fd7463ce89. Suite: 4308 tests, 1 skipped, 2 failures in 500.708s.

Eleven alias-lane tests (all PASSED):
- CaptureSeparatorToggleTests.testPeriodAliasAfterRouteOpensNewIDBlockPicker PASSED (0.229s)
- CaptureSeparatorToggleTests.testNativeUndoRestoresLiteralSigilAliasWithoutRetriggering PASSED (0.209s)
- CaptureSeparatorToggleTests.testDelayedAcceptedAliasSupersedesGatedCompletion PASSED (0.479s)
- CaptureSeparatorToggleTests.testPeriodAliasOnMoveBulletOpensMovePicker PASSED (0.167s)
- CaptureSeparatorToggleTests.testSemicolonAliasOnOfferMoveBulletOpensMoveAndLinkPicker PASSED (0.265s)
- CaptureSeparatorToggleTests.testUndoAfterMoveAliasRestoresLiteralWithoutRetriggering PASSED (0.326s)
- CaptureSeparatorToggleTests.testCommaAfterCompleteTargetRunOpensNextParentPicker PASSED (0.175s)
- CaptureSeparatorToggleTests.testBackslashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.553s)
- CaptureSeparatorToggleTests.testSlashAliasAfterTaskTypeOpensTypeMenuAndDoubleTapCloses PASSED (0.424s)
- CapturePanelModelTests.testCommaOnExactRouteUsesBobRewriteLane PASSED (0.257s)
- CapturePanelModelTests.testCommaCommitsPartialRouteThenBobOpensParentTaskPicker PASSED (0.139s)

Previously in-scope regressions now PASSED on this narrowed dismiss hook:
- CaptureSeparatorToggleTests.testSemicolonAliasAfterRouteOpensLinkModeBlockPicker PASSED (0.091s)
- CaptureRelatedLaneTests.testNoSpawnWhileModalOwnsPanel PASSED (0.432s) (failed on snapshot 42381542095)
- CaptureRelationEqualsAliasTests.testEqualsAliasOpensLinksToAndCallsRewriteBeforeCompletion PASSED (0.407s)
- CaptureRelationEqualsAliasTests.testTildeFlipFastEqualsAfterPickerRestoresTildeEquals PASSED (0.272s)
- CaptureRelationEqualsAliasTests.testTripleEqualsGivesDoubleEquals PASSED (0.300s)

Other failures on the same job:
- CaptureEditorWordMotionTests.testMotionsLeaveTextAndUndoUntouched FAILED XCTAssertFalse line 67 — same as master 42337582432 (word-motion sibling). After this snapshot, origin/master moved 1e0a092..2a089e5 ("keep word motions out of undo history"); that commit touches CapturePanelController.swift and CaptureEditorWordMotionTests.swift only. Dirty alias-lane tree rebased cleanly onto 2a089e5.
- CaptureSeparatorToggleTests.testRelationDashIntentForwardsUngatedInTheMainEditor FAILED XCTAssertTrue at line 398 (`afterTab`) in 1.653s. Helper `relationDashWasForwarded` sleeps 160ms then reads the fake-bob record. Same test PASSED on master 42337582432 (1.460s), snapshot 42378175085 (1.612s, harness-only), and snapshot 42381542095 (1.698s, blanket dismiss). This helper never opens a picker, so `shouldDismissPickerAfterEditorDraftChange` is a no-op. Parent design names this 160ms sleep as the flakes-phase timing-sensitive example.

PROPOSED FOLLOW-UP: Harden CaptureS

… and 10879 more characters

## Dependencies

- **Blocks:** [sase-1rq.4.1.3](sase-1rq.4.1.3.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.1.md) | [sase-1rq.4.1.1](sase-1rq.4.1.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.4.1.1--3][1] | Need assigned bead notes before recording this CI snapshot | 1 |
| read-by | [agent:sase-1rq.4.1.1--5][1] | Need current notes and inherited decisions before scoring the green alias-lane snapshot | 1 |
| read-by | [agent:sase-1rq.4.1.land][2] | Review all remaining alias-lane notes without truncation | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.land/README.md

<!-- sase:referenced-by:end -->
