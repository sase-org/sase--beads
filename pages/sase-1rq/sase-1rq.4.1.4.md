# Bead: sase-1rq.4.1.4 — Drive master CI green and publish evidence

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.4` · **Size:** medium
**Created:** 2026-11-07 08:03:37 EST · **Closed:** 2026-11-07 14:49:53 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

master-green: watch bob-mac-capture master CI after every fix phase has landed. Repair any quick new regression that concurrent bob-cli agents landed, get a green first-attempt run at or after the last fix commit, and publish `ci_evidence` (or the fallback research report) for the parent phase sase-1rq.4.

## Notes

[2026-11-07T19:49:28Z · sase-1rq.4.1.4] PROPOSED FOLLOW-UP: Replace or delete the always-skipped placeholder CaptureCoreTests.ProjectTaskMovePickerPresentationTests.testResponseDecodesMoveHeader in bobs-org/bob-mac-capture — since c0dd1e2 (2026-11-03) it looks up move-complete-mc1.json via Bundle(for: Self.self), but the CaptureCoreTests target declares no resources, so it always throws XCTSkip("move-complete-mc1 fixture missing") and asserts nothing even when found. It is the 1 skip in every green run (e.g. master run 42405431372). Either load Tests/Fixtures/move-complete-mc1.json by #filePath and decode the move header, or delete the stub. Suggested task_type: bug.

[2026-11-07T19:49:33Z · sase-1rq.4.1.4] PROPOSED FOLLOW-UP: Give agents a way to run the bob-mac-capture XCTest suite locally — the tailnet mac (macOS 26.5) has only Command Line Tools with no XCTest.framework, so every test is only type-checked locally and first runs on CI; this is the structural reason 12 never-passing tests piled up on master. Options for Bryan: install full Xcode on the mac, or provide another macOS host with Xcode. Suggested task_type: feature.

[2026-11-07T19:49:38Z · sase-1rq.4.1.4] master-green evidence: master tip c2b7db24f188285085babb13570ae11f825ae197 (= last fix commit of epic sase-1rq.4.1; no later commits). Push CI run 42405431372 (https://github.com/bobs-org/bob-mac-capture/actions/runs/42405431372, job "macOS 26 SwiftPM" 128501989160), attempt 1, conclusion success, completed 2026-11-07T19:33:53Z. Test: Executed 4309 tests, 1 skipped, 0 failures (0 unexpected) in 492.174s. Lint, Build, Test, Bundle, Verify plist and signature, Launch smoke test, Install and reinstall all success. First-attempt green; no rerun used. Fix chain 1e0a092..c2b7db2 is exactly 2a089e5 (word-motion), d94d912 + fb22462 (alias-lane), c2b7db2 (flakes). Quarantined: none. This phase landed no code: master was already green when it started. Published ci_evidence via sase var. Earlier PROPOSED FOLLOW-UPs on sibling phases (relation-tilde/dash/equals 160ms sleeps) were resolved by c2b7db2 and need no beads.

[2026-11-07T19:49:53Z · sase-1rq.4.1.4] Master tip c2b7db2 (last fix commit of epic sase-1rq.4.1) is green on the first attempt: CI run 42405431372, push, conclusion success, 4309 tests, 1 pre-existing placeholder skip, 0 failures. Bundle, Verify plist and signature, Launch smoke test, and Install and reinstall all succeeded. Fixes: 2a089e5, d94d912, fb22462, c2b7db2. No tests quarantined. Published ci_evidence via sase var. Recorded 2 PROPOSED FOLLOW-UPs: the always-skipped testResponseDecodesMoveHeader stub, and no local XCTest on the mac. No epic-symbol leftovers. Ancestors left open.

## Dependencies

- **Depends on:** [sase-1rq.4.1.1](sase-1rq.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rq.4.1.2](sase-1rq.4.1.2.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rq.4.1.3](sase-1rq.4.1.3.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.4/README.md) | [sase-1rq.4.1.4](sase-1rq.4.1.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.4.1.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.land/README.md

<!-- sase:referenced-by:end -->
