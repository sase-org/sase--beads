# Bead: sase-1kx.5 — Finish v0.18.0 watcher correctness, visual proof, and publication

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.land.md) · **Assignee:** `sase-1kx.5.land`
**Created:** 2026-10-14 09:33:40 EDT
**Plan:** [202610/v0\_18\_0\_release\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_finish.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_0_release_finish.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:280388d2d1c4308e7a8bbe18 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_finish.md

<!-- sase:links:end -->

## Description

The remaining release watcher defects are fixed, the complete visual lane is clean, and sase 0.18.0 is published and installable through the guarded release flow.

## Notes

[2026-10-14T19:26:10Z · sase-1kx.5.land] LANDING AUDIT (2026-10-14, HEAD and fetched origin/master 4d8940d4b7e102c1f6e031f4b59e3642fdbd2931): reviewed this epic, both children, every child note, the linked plan and parent DECISIONS, actual changed source and commit 960f1e1b670a6993ef885506359f9b3166ae318b, and all concurrent changes since creation (docs 613d4b2acb/8671366a27, ACE-test split de27bceedf, E3 d070e6b2dc, watcher split 79c1b5d958, Argon/ToolRun 4d8940d4b7). No missing integration in those changes; use the split watcher modules for remaining coverage. All 32 watcher test functions survive the split, and 46 parametrized tests pass independently in 4.48s. Verified .5.1 ToolRun 933abe374ee28172dfa8b09d2c1bd597 really succeeded: argv just check, exit 0, triage pass.

NOT READY TO CLOSE. .5.1's local clean visual proof did not hold remotely: Full CI 38604579828 at d070e6b2dc17 passed 1366 visual tests but drifted five PNGs (0 created, 5 updated, 1095 unchanged, 0 stale). Inspected all expected/candidate pairs and fixture/production paths. Exact findings: turns_gate_90x40 loses (/) blocks (14707 pixels); weighted_runner_capacity_expanded_80x32 loses the same action (16318); archive_list_120x40 summary says 0 versus 2 matching members (1919); session_lane_neighbors_160x50 changes active Context/Reply and scrollbar (3570); artifacts_split_selected_wide_120x40 changes only the detail scrollbar (1903). Durable report with images and SVG: file:explicit:280388d2d1c4308e7a8bbe18. This is the existing whole-visual-lane release criterion, not a check-full-only failure. No just check-full was run.

.5.2 notes #1-2 are accounted for: its preflight needed NO_COLOR=1 GH_FORCE_TTY=0 because forced color corrupted gh JSON; the monitor correctly stopped on actual executed drift markers and closed canceled FULL_CI_RED. Core 0.40.0 is now on PyPI, pin remains a89eac09, and #299 floor smoke is green. Publish 38599345547 only ratcheted metadata (build and publish skipped). #299 remains OPEN, PyPI sase is 0.17.1 without 0.18.0, and GitHub v0.18.0 is absent. Master Gate 38610666059 is green on current HEAD; newer Full CI 38616988827 was still in flight. Preserve dispatch/notes decisions; no duplicate core dispatch, manual merge, or agent cancellation performed.

Independent source probes also expose unfinished watcher contracts: echoed literal echo/printf SASE_VISUAL_REPORT_STATUS=drift is accepted as execution; combined-log fallback can lose visual job identity; core_version_meets accepts higher 0.41.0rc1 and malformed 0.41.0garbage against stable 0.40.0. Startup signals and blank completed conclusions are correctly fixed. Normalize gh machine-output environment and cover the remaining cases.

FOLLOW-UP TRIAGE COMPLETE: exactly one PROPOSED FOLLOW-UP, .5.2 note #3 (Full CI visual red). Retained as required release work; declined a new omnibus task. Used sase_new_task, searched CI and all-type tasks across statuses, reviewed sase-x5 and sase-10u, swept all 104 tasks from the last week, and reviewed active epic scopes plus sase-1jz/.3. These live capture-state defects differ from the historical static title/r/R/V goldens, so no +1 to those tasks. Added DISCOVERED ISSUE to sase-1jz for the concrete causal gate-footer/deck overlap with evidence. Archive-summary and detail-scrollbar drifts stay in the already approved full-lane scope; no speculative product-defect tasks. Watcher bugs remain epic work. Preserve parent sase-1kx's earlier dispositions (sase-1ky, sase-1kz, sase-172, sase-xo, sase-1ic, sase-1gn and explicit declines) in final closure.

sase bead epic-symbols sase-1kx.5 reports none. Epic and plan remain in progress. Preparing a validated two-phase child epic: one medium coding phase, then one small no-edit release proof on its landed commit. A tale cannot satisfy the required post-commit remote CI/publication proof in its coding turn. The child parent_bead is sase-1kx.5; its landing resumes this epic and then sase-1kx with full descendant/linked-plan readiness, symbol retirement, normal closes, symvision, and done-frontmatter updates. No forced close. Plan passed --explain validation, was refined, and passed revalidation without --explain (0 warnings).

[2026-10-15T02:34:58Z · sase-1kx.5.3.land] PARENT LANDING BLOCKER: child sase-1kx.5.3 remains incomplete. Its landing audit independently verifies the check pass and 60 watcher tests, but Full CI 38653006628 still has five real ACE capture mismatches (file:explicit:3435087f16e0e38529c2fe7f), no 0.18.0 publication, and no required clean full visual proof. Current origin/master is 2465bc7a18. All child follow-ups are triaged on the child landing note (sase-1f9, sase-1l5, sase-1a2, sase-1ii, causal note to sase-1jz; separate newer smoke flake sase-1l6). A validated two-phase remaining-work child epic is being proposed under sase-1kx.5.3 because publication proof must follow the future repair commit. Keep this parent and its plan in progress; preserve dispatch/notes decisions and earlier follow-up dispositions.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.land.md) | [sase-1kx.5](sase-1kx.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kx.5.3.3.1--2][1] | Need project epic decisions relevant to this assigned child phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.3.3.1.md

<!-- sase:referenced-by:end -->
