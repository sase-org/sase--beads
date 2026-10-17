# Bead: sase-1lh.7.5 — Finish recapture correctness and release gate integration, then confirm sase v0.18.0

[Bead Pages](../README.md) / [sase-1lh.7](sase-1lh.7.md) / sase-1lh.7.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.land.md) · **Assignee:** `sase-1lh.7.5.land`
**Created:** 2026-10-16 20:23:07 EDT
**Plan:** [202610/finish\_recapture\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_recapture_release.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_recapture_release.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:6342ab3533376d4bbfa3d04f | attached via sase artifact create --bead |
| related | file:explicit:68a2c07fd2b673bf2fa2cc23 | attached via sase artifact create --bead |
| related | file:explicit:cb9fb741595e074b5783a449 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_recapture_release.md

<!-- sase:links:end -->

## Description

Check-mode recapture preserves execution and completeness failures and obeys its wall-clock budget. Current release gates and visual checks pass, ci_watch merges PR 299, and sase 0.18.0 installs from PyPI, allowing sase-1lh.7 and its parent sase-1lh to finish their landing audits.

## Notes

[2026-10-17T03:10:01Z · sase-1lh.7.5.land] LANDING AUDIT AND FOLLOW-UP TRIAGE (2026-10-17 UTC, master 4cb33feae9): incomplete; do not close or mark plan done. Full audit file:explicit:6342ab3533376d4bbfa3d04f; bounded repro script file:explicit:68a2c07fd2b673bf2fa2cc23.

Read this epic, all three children and every note, linked plan and both parent landing notes/plans, source, implementation commits 499c825cb9/f564f0f996, all five later non-epic commits and four concurrent commits since epic creation; fetched origin/master equals HEAD. Verified strict check-mode recovery and scope handling, retry validation, Python help portability, launch timestamp integration, narrow storage-identity exemption, and the four inspected PNGs. Split watcher decision tests now require the three real test modules, not their __test__=False facade. 58 focused recapture/timeout/launch tests and 118 watcher/audit/base/verify/salvage tests pass. tools/check_docs exits 0 (three known Contribute warnings). No tracked code edits or check-full run. epic-symbols sase-1lh.7.5 reports none.

REMAINING EPIC WORK: early stdout/stderr EOF bypasses the deadline via unbounded proc.wait(): 0.15s budget returns success after 1.216s for a 1.2s sleeping child. TERM cleanup reaps the leader but leaves its TERM-ignoring descendant alive (state S); SIGKILL escalation checks only leader liveness. Existing tests miss both cases. Repair these in the epic, not tasks.

RELEASE: .3 closed canceled honestly. PR #299 is still OPEN but now targets 0.17.2, head 043f8a95eebbc72ef26fcbbb6553192b1af4bc64; Publish 38996094567 regenerated it but skipped build/publish. Live PyPI has sase 0.17.1, no 0.18.0, and core 0.40.1. The configured pre-1.0 feature policy selects patch releases; no Release-As: 0.18.0 commit exists. Verified upstream documented one-time commit-body Release-As mechanism via audited external checkout. The repair coder must include that trailer in its host final declaration; a separate no-edit phase verifies the actual commit, regenerates the PR through normal Publish, and watches exact 0.18.0. No manual release merge, branch push, or dispatch by this lander. Master Gate 38996356739 has an independent New Project readiness flake; Full CI 38996026102 was in flight.

EVERY PROPOSED FOLLOW-UP OUTCOME, triaged through sase_new_task:
- sase-1lh.7.5.1 note 1: duplicate of existing sase-1lw, already repaired in f564f0f996. Affected launch/TUI/macro-group tests pass. Closed sase-1lw with verification; declined duplicate/+1 for a fixed defect. This also addresses .2 DISCOVERED ISSUE note 1.
- sase-1lh.7.5.2 note 2: all seven E5 prose violations removed by docs-owner 08d9b66154. Current check_docs passes. Declined new task because resolved; no active-epic issue remains to route.
- .2 note 3 repeats those same outcomes. Its separate retry-ID observation is already corroborated on sase-173 with freeze-before-harness evidence and two zero-unstable checks. No duplicate task or new +1; this audit inspected the goldens/source but did not repeat visual capture or broadly close the flake.
- Also closed already-repaired sase-1lx and its exact duplicate sase-1ly after source review and the full passing project-presentation audit.
- Newly discovered independent Master Gate failure: created small flake task sase-1m9, related to adjacent sase-1l8, evidence file:explicit:cb9fb741595e074b5783a449. test_review_back_restores_draft_and_y_stores_model_submission fails on Review.disabled after a fixed 0.4s pause in CI and passes locally on the identical source SHA (1 passed/7.54s). The mocked preview still uses a real 0.3s debounce. No claim of an identical runtime environment or measured general fail rate. All-status searches, last-week task sweep, active-epic review, and closed New Project epic sase-1jx exclude duplicates/active causal ownership.

NEXT: two-phase child epic sase_plan_finish_deadline_release_target.md with parent_bead sase-1lh.7.5, deadline-repair (medium) then release-watch (small). Both --explain validation and final revalidation passed with zero warnings. Epic instead of tale because required publication must contain the coder's post-turn host commit and release trailer. Parent closeout is a land-agent duty, not a phase. The child lander must confirm all six release criteria, then recheck/close sase-1lh.7.5 normally, symvision, mark plan:202610/finish_recapture_release.md done; then recheck parent sase-1lh.7 and sase-1lh, including original post-release/stale-epic duties. Never force a successful nested landing; note and stop at the first incomplete parent.

[2026-10-17T04:20:34Z · sase-1lh.7.5.4.land] CHILD LANDING BLOCKER: sase-1lh.7.5.4 deadline repair is verified (151 focused tests pass), but its no-edit watcher closed canceled. Exact release-please 17.6.0 parsing of the host commit ignores Release-As before SASE provenance; a supported nested-commit block is verified to preserve the release directive. PR #299 remains 0.17.2 and PyPI 0.17.1. Current provenance/config integration failures are routed to sase-1m3 and the remaining-work child plan; recurring flake evidence is routed to sase-1ls, sase-1a7/sase-1i5, and existing sase-j7 note #78. The current child remains open and its linked plan is not done. See its full landing audit; no force-close or release success claim.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.land.md) | [sase-1lh.7.5](sase-1lh.7.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.1--1][1] | Need parent epic scope and DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.1.md

<!-- sase:referenced-by:end -->
