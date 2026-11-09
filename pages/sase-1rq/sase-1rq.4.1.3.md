# Bead: sase-1rq.4.1.3 — Harden or quarantine the intermittent alias and card tests

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.3` · **Size:** medium
**Created:** 2026-11-07 08:03:37 EST · **Closed:** 2026-11-07 14:41:10 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

flakes: after alias-lane lands, classify each intermittently failing test: still failing, timing-sensitive (harden it), or a proven flake on an unchanged tree (quarantine it under the parent test_quarantine decision). Leave the suite with no known intermittent failures.

## Notes

[2026-11-07T18:31:28Z · sase-1rq.4.1.3] Classification (evidence = --log-failed of 39 failed CI runs back to 42212293089; snapshot trees diffed against their bases). Base master fb22462.

TIMING-SENSITIVE, hardened in this phase (uncommitted tree, pending 2 unfiltered macos-ci-check runs):
- CaptureSeparatorToggleTests.testRelationEqualsIntentForwardsAtOpenerPositionsAndRelationEnds (XCTAssertTrue afterTilde/afterSpace; runs 42291752860, 42301790718, 42395563068 master fb22462), testRelationDashIntentForwardsUngatedInTheMainEditor (afterTab; 42384626815), testRelationTildeOnlyForwardsAtBobReportedRelationEnd (afterRelation; 42380490392 master 2a089e5). All are positive asserts that missed the fixed 160ms sleep in relation{Dash,Equals}WasForwarded. Fix: new CapturePanelModel.rewriteInFlightForTesting (rewriteTask != nil; every captureRewrite launch sets it synchronously) decides forwarding right after the edit; forwarded keys then poll the fake-bob record (5s cap) instead of sleeping.
- CaptureSeparatorToggleTests.testTypedCommaInCloseTaskListStaysLiteralForCloseGrammar (line 1352 rewrite record missing on master 1e0a092 42337582432; passed on snapshot 41b5e59 of the same tree). isClosePending comes from parse, which races the rewrite. Fix: assert rewrite launched, wait for isClosePending && !rewriteInFlight before the literal-comma and record checks.

ALREADY FIXED BY EARLIER COMMITS (no change):
- CaptureRelationFlipAliasTests.testLabeledRelationTildeFlipsAndEqualsStaysLiteral: NSCocoaError 260 before 1e0a092, which made it poll the record; 0 failures in 9 runs since.
- CaptureRelationEqualsAliasTests.testFastSecondEqualsUndoesOpenerAfterReply / testEqualsGestureGuardsRepeatMarkedTextAndZeroTimestamps: red only on introducing commit 4fbbe84 (42323414005), fixed by 1e0a092.
- CapturePullInChoiceTests.testFooterContractPinsHintsAndAccessibilityText and CaptureMoveChoiceModelTests.testMoveThenPullInBackAndInboxCarryOneAnswerAndSeed: deterministic through e9d3ae2/414874e, fixed by 5b0dca6; 0 failures in ~30 runs since.

HOSTED ALIAS-OPEN TIMEOUTS (fail+pass on unchanged trees; none since d94d912):
- testEqualsAliasOpensLinksToAndCallsRewriteBeforeCompletion: failed 42337610556 (41b5e59 = 1e0a092 + one FlipAlias test edit), passed 42337582432 (1e0a092). Rewrite recorded, capture-complete never recorded in 10s, picker never opened.
- testTripleEqualsGivesDoubleEquals: failed 42376806344 (af52c1d), passed 42380490392 (2a089e5, byte-identical tree). openTimestampedAlias 10s timeout.
- CaptureHashAliasDoubleTapTests.testSlowDoubleTapClosesMenuWithOneLiteralBackslash (2e21f77 ~ 418604a: failed 42310508038, passed 42301790718), testSlowSlashDoubleTapClosesMenuWithOneLiteralSlash and CaptureRelationFlipAliasTests.testArmedDashEqualsFlipsInsteadOfRestoring (f1a0649 == cbb50dc Sources/Tests: failed 42278074963, passed 42278025697). Same shape: hosted editor, alias rewrite, completion never shows.
Not quarantined yet: 0 recurrences in the 4 runs since d94d912/fb22462 (which changed the expand_sigil_alias analysis path). Added a state + fake-bob argv dump to these waits' timeout messages so the next occurrence can be diagnosed. If one recurs on this phase's proof runs it gets quarantined under test_quarantine.

Compile: just portable-check on athena PASS (2264 tests); mac scratch bundle.sh + just typecheck-tests PASS (copy deleted).

[2026-11-07T19:13:38Z · sase-1rq.4.1.3--1] Proof runs (monitor acdk46, two unfiltered Scripts/macos-ci-check snapshots of the same uncommitted tree, base master fb22462, started 20s apart):
- Run 1: GH run 42401972251, snapshot 42179623122abc9bd338226b6078ff63cc2fa6a5, exit 0, Executed 4309 tests, 1 skipped, 0 failures; all 16 macOS job steps ok.
- Run 2: GH run 42401998833, snapshot ff2b42d2bfd7d7aa20d2058d35753acfd11b30a8, exit 0, Executed 4309 tests, 1 skipped, 0 failures; all 16 macOS job steps ok.
Failed tests: none in either run. The single skip in both is CaptureCoreTests.ProjectTaskMovePickerPresentationTests.testResponseDecodesMoveHeader (pre-existing XCTSkip 'move-complete-mc1 fixture missing' already on master, untouched by this phase).
Phase-list tests passed in BOTH runs: CaptureSeparatorToggleTests.{testRelationEqualsIntentForwardsAtOpenerPositionsAndRelationEnds, testRelationDashIntentForwardsUngatedInTheMainEditor, testRelationTildeOnlyForwardsAtBobReportedRelationEnd, testTypedCommaInCloseTaskListStaysLiteralForCloseGrammar}, CaptureRelationEqualsAliasTests.{testEqualsAliasOpensLinksToAndCallsRewriteBeforeCompletion, testTripleEqualsGivesDoubleEquals}, CaptureHashAliasDoubleTapTests.{testSlowDoubleTapClosesMenuWithOneLiteralBackslash, testSlowSlashDoubleTapClosesMenuWithOneLiteralSlash}. CaptureRelationFlipAliasTests.testArmedDashEqualsFlipsInsteadOfRestoring no longer exists (removed by 418604a, an ancestor of fb22462), so nothing to quarantine. No quarantine needed: 0 hosted alias-open timeouts on this tree.
origin/master still fb22462 at land time, no rebase. Landing as one commit; follow-up monitor watches the landed master SHA's CI run before this phase closes.

[2026-11-07T19:40:57Z · sase-1rq.4.1.3--2] Landed + master CI: commit c2b7db24f188285085babb13570ae11f825ae197 (test(mac-capture): replace fixed sleeps in rewrite-lane forwarding tests) is origin/master, parent fb22462. Push CI run 42405431372 (workflow CI, job "macOS 26 SwiftPM" 16m55s) conclusion SUCCESS: Executed 4309 tests, 1 skipped, 0 failures (0 unexpected); 0 failed test cases in the log. Only skip is the pre-existing CaptureCoreTests.ProjectTaskMovePickerPresentationTests.testResponseDecodesMoveHeader (fixture-missing XCTSkip). All 8 phase-list tests passed on master: CaptureSeparatorToggleTests.{testRelationEqualsIntentForwardsAtOpenerPositionsAndRelationEnds 0.320s, testRelationDashIntentForwardsUngatedInTheMainEditor 0.270s, testRelationTildeOnlyForwardsAtBobReportedRelationEnd 0.096s, testTypedCommaInCloseTaskListStaysLiteralForCloseGrammar 0.151s}, CaptureRelationEqualsAliasTests.{testEqualsAliasOpensLinksToAndCallsRewriteBeforeCompletion 0.399s, testTripleEqualsGivesDoubleEquals 0.437s}, CaptureHashAliasDoubleTapTests.{testSlowDoubleTapClosesMenuWithOneLiteralBackslash 0.702s, testSlowSlashDoubleTapClosesMenuWithOneLiteralSlash 0.614s}. Previous master run 42395563068 (fb22462) was red on testRelationEqualsIntentForwards...; this run is green. No quarantine was needed. Hardened tests are now 3/3 green (two snapshots + master).

[2026-11-07T19:41:10Z · sase-1rq.4.1.3--2] Landed c2b7db24f188 on bobs-org/bob-mac-capture master; push CI run 42405431372 SUCCESS (4309 tests, 1 pre-existing skip, 0 failures). All 4 hardened rewrite-lane tests and all 4 hosted alias-open tests passed there and in both proof snapshots (42401972251, 42401998833). Card and labeled-tilde intermittents were already fixed upstream (5b0dca6, 1e0a092); no quarantine needed. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1rq.4.1.1](sase-1rq.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ✓ · ⧖ 2026-11-07

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.4.1.3--1][1] | Continue flakes phase after CI snapshot monitor; need notes | 1 |
| read-by | [agent:sase-1rq.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.land/README.md

<!-- sase:referenced-by:end -->
