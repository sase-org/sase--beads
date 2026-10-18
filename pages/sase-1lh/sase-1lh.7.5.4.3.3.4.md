# Bead: sase-1lh.7.5.4.3.3.4 — Repair portable core publication and the remaining sase release gates

[Bead Pages](../README.md) / [sase-1lh.7.5.4.3.3](sase-1lh.7.5.4.3.3.md) / sase-1lh.7.5.4.3.3.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.5.4.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.land.md) · **Assignee:** `sase-1lh.7.5.4.3.3.4.land`
**Created:** 2026-10-17 17:10:44 EDT
**Plan:** [202610/finish\_release\_gate\_fixtures.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_gate_fixtures.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_release_gate_fixtures.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:0c00d9b69c28858fb5069bf4 | attached via sase artifact create --bead |
| related | file:explicit:ce30efab790c5cca3efd1466 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_gate_fixtures.md

<!-- sase:links:end -->

## Description

Repair the core macOS compile failure and two Master Gate blockers, observe a compatible published core and sase 0.18.0, and return the incomplete landing to sase-1lh.7.5.4.3.3.

## Notes

[2026-10-18T01:52:28Z · sase-1lh.7.5.4.3.3.4.land] LANDING AUDIT / FOLLOW-UP DISPOSITIONS (2026-10-18 UTC): NOT COMPLETE. Read this epic (initially no own notes), all three child scopes and every note, its linked plan plan:202610/finish_release_gate_fixtures.md, and the previous parent landing notes/plan. Phase .1 commit dd56b94a8ad9fdca541d16cb5b6f85a2b45e55af fixed the fixed-argument mode_t mismatch but introduced macOS E0617 at both variadic openat calls, fs.rs:191 and :393. Verified actual core source, full commit diff, pending core PR #331 containment, and CI 39071544870 job 117510033363. Linux check 5baf8fd82840a8a99ce136b0871bd3d4 really passed; it cannot prove macOS. The sole PROPOSED FOLLOW-UP, phase .3 note #1, is caused by this epic and stays required work; declined a standalone task and the claim that it is a separate pre-existing compiler error. Retained log file:explicit:ce30efab790c5cca3efd1466.

Phase .2 commit 933970ce72a5b5328499e80751a491c857bfc221 pins that core and explicitly supplies/asserts the fixture submission timestamp under unset and hostile ambient input; common env and global-state isolation changes are present. Strict rescue audit now names _rescue_git.py:_rescue_git_repo_body, with the correct reviewed deletion scope, provided by concurrent 5cf773c154. Verified ToolRun 775bb391c2dc9975321fcc238552c690 really succeeded (just check, all stages, exit 0), and monitor s4rqbkt02qrj really ran ten Python 3.12 tutorial attempts with fresh HOME/basetemp and CI=1, concluding TUTORIAL_ATTEMPTS=10 TUTORIAL_FAILURES=0. Existing date-sweep disposition is recorded on .2; no date fix was needed there. Independent focused audit ea71a0a3feee0de027d98bfdd22a332a passes 10 tests: deferred workspace module, directory operation audit, and new-project collision node.

INTEGRATION: fetched both origin/master branches; neither has post-fix master commits. Reviewed all intervening non-epic sase splits 0f91d5eed0 (runner-utils tests), cc64a8e8e6 (tutorial helpers), 57e0e97874 (rescue tests), plus baseline-race rescue split 5cf773c154 and release-branch metadata commits eca5854b91/d3f2ba36c7. Facades retain imports; tutorial STARTING/DONE recognition, previous-name exclusion, disk fallback, and bounded diagnostics survive the split. The rescue audit is already integrated. The release branch correctly proposes 0.18.0 and ratchets to published core 0.41.0; that wheel still lacks the required new pairing capability, so do not blindly change master metadata. No other integration gap found.

RELEASE: phase .3 closed canceled, not done, with MASTER_GATE_RED. Current Master Gate 39077497974 fails the New Project collision node on both attempts; PR #299 remains OPEN/UNSTABLE at d3f2ba36c7580e1da8ba9a9eaf90016e1da8b1fc. Core #331 remains open at 0b23a73917eca7c140c3ffcb651c73d1daddf39f with failing macOS CI. PyPI still serves sase 0.17.1/core 0.41.0, neither sase 0.18.0 nor core 0.42.0; GitHub v0.18.0 absent. Publish 39077813839 skipped actual publication. Full CI 39085508146 was still running. Preserved dispatch=yes, visual_flakes=recapture, stale_epics=supersede; no manual merge, dispatch, version edits, or force close.

FOLLOW-UP TRIAGE via sase_new_task: all-status searches, last-week task sweep, and in-progress epic review completed. New independent flake sase-1mi (large, READY) records watch phase .3 note #2: test_name_collision_blocks_review_but_occupied_checkout_surfaces leaves Review enabled in both CI attempts and passes locally on the same unchanged source SHA. CI Python 3.12 versus local 3.14 is documented; no general failure rate or proven cause claimed. Related sase-1m9 and sase-1l8 are different configure-preview and visual-create failures, not demonstrated duplicates. Original New Project epic sase-1jx is closed, and no active causal owner was found. Retained CI evidence file:explicit:0c00d9b69c28858fb5069bf4 is attached to the task. The first-attempt link-follow failure is existing sase-1lr and passed the rerun; supplemental evidence recorded there, with its approved repair exclusion preserved. No other proposal appeared on .1 or .2. All earlier parent follow-up dispositions remain standing.

EPIC SYMBOLS: sase bead epic-symbols sase-1lh.7.5.4.3.3.4 is empty. No tracked source edits and no check-full run. This epic and all ancestors remain open; no plan marked done. Remaining plan has only core variadic promotion, a subsequent committed pin/compatibility phase, and a no-edit publication watch. The separate commit boundaries are required for real release proof; one tale cannot close this release scope in its coder turn. Original plan/parent closeout stays with the successful child landing continuation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land.md) | [sase-1lh.7.5.4.3.3.4](sase-1lh.7.5.4.3.3.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.4.3.3.4.1][1] | Need parent epic DECISIONS and phase notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.1/README.md

<!-- sase:referenced-by:end -->
