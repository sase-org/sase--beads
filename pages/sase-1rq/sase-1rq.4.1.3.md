# Bead: sase-1rq.4.1.3 — Harden or quarantine the intermittent alias and card tests

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.3` · **Size:** medium
**Created:** 2026-11-07 08:03:37 EST
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

## Dependencies

- **Depends on:** [sase-1rq.4.1.1](sase-1rq.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.3.md) | [sase-1rq.4.1.3](sase-1rq.4.1.3.md) | 0 |
