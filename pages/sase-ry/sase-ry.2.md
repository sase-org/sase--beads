# Bead: sase-ry.2 — Wait for ci\_watch to submit the green release PR

[Bead Pages](../README.md) / [sase-ry](README.md) / sase-ry.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0a1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0a1.md) · **Assignee:** `sase-ry.2` · **Size:** small
**Created:** 2026-08-21 18:56:04 UTC
**Plan:** [202608/release\_v0\_17\_0.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_v0_17_0.md)

## Description

await_ci_watch_submission: confirm ci_watch is healthy and responsible for PR 284, then use a dedicated SASE monitor and successor agent to wait for the chop to submit the PR without manually merging it.

## Notes

[2026-08-21T19:28:22Z · sase-ry.2] Progress: confirmed ci_watch is the configured release-merge chop for sase-org/sase (release-please, merge_enabled=true, merge_order last among sase-core/sase-github/sase-telegram/sase). AXE is RUNNING/HEALTHY; lumberjack ci_watch PID 2506900, interval 5m, cycles=7 errors=0, chop doctor OK. PR 284 remains OPEN (head 3729194ae294f9dd0f4be0fd966f179edff7bb87); required checks terminal: Conventional PR title SUCCESS, release-core-floor-smoke SUCCESS in run 32517366859/job 96881903588 completed 2026-08-21T19:15:00Z, source lanes SKIPPED. No SASE Patch for PR 284 has been adopted yet. Last live ci_watch sweep is stale (releases.report.json updated 08-21 04:58, still labels #284 "base branch not green") because every tick since 18:51 UTC was skipped: inhibited by agent_runners max=0. Live slot holders include this phase and sase-ru.6--mon (WAITING RELEASE for v0.17.0). Starting WAITING FOR SUBMIT / SUBMITTED monitor; will not merge.

[2026-08-21T19:28:54Z · sase-ry.2] PROPOSED FOLLOW-UP: ci_watch inhibit_if.agent_runners counts monitor proc shells — sase-ru.6--mon is WAITING RELEASE for v0.17.0 while holding a runner slot, so the chop that must merge PR 284 stays skipped; consider excluding monitors from that guard or not occupying a slot during release waits.

[2026-08-21T20:31:17Z · sase-ry.2--1] Progress: monitor 6a03sp1v57vw timed out after 55m23s (exit 124). PR 284 remains OPEN, MERGEABLE, CLEAN at https://github.com/sase-org/sase/pull/284 head e725dc0afb243eb85abd363c9173073698768ae1. Required checks still terminal (Conventional PR title SUCCESS; release-core-floor-smoke SUCCESS in run 32522696721/job 96898135182 completed 2026-08-21T20:17:36Z; source lanes SKIPPED). No SASE Patch adopted for PR 284. This is a real automation fault, not an ordinary 5m tick: AXE HEALTHY, ci_watch PID 4156499 errors=0, but every scheduled tick is skipped by inhibit_if.agent_runners.max=0. Latest skip 20260821T203018_980031 reason "inhibited by 9 agents holding runner slots (e.g. sase-rr.5.2)". releases.report.json still stale (mtime 2026-08-21T08:58:27Z, labels #284 "base branch not green"). Persistent slot holders include sase-ru.6--mon (WAITING RELEASE for v0.17.0 since 16:36Z) plus this phase family. sase-core#152 is now MERGED; sase-telegram#19 remains OPEN CLEAN so merge_order can still delay sase by one tick after inhibit lifts. Current master CI run 32522425294 is pending with no jobs since 20:12:58Z — a possible later default_branch_not_green guard, unevaluated while the chop is skipped. In-flight tale plan:202608/simplify_ci_watch.md (agent 0a6) already removes ci_watch.chops.ci_watch.inhibit_if; not proposing a competing plan. Starting a second WAITING FOR SUBMIT / SUBMITTED monitor. Will not merge.

[2026-08-21T20:31:19Z · sase-ry.2--1] PROPOSED FOLLOW-UP: do not duplicate 0a6 simplify_ci_watch — that tale already deletes ci_watch inhibit_if; if it fails to land, exclude monitor proc shells from agent_runners occupancy or drop max=0 so sase-ru.6--mon WAITING RELEASE and this phase wait cannot deadlock PR 284.

[2026-08-21T22:42:53Z · sase-ry.2--2] Progress: monitor p78mp6h7tkx1 timed out after 2h0m (exit 124). PR 284 still OPEN MERGEABLE UNSTABLE at https://github.com/sase-org/sase/pull/284 head e4f917901734b2d79cb53d6d0c8fd2b6a8f539af. 0a6 simplify_ci_watch has landed: AXE restarted 2026-08-21T20:50Z, inhibit_if.agent_runners.max=0 is gone, ci_watch PID 487913 cycles=21 errors=0 now runs the chop. Live skip is not an ordinary interval: ci_watch.report.json 22:33:12Z labels #284 "base branch not green" because master@6639a2801616 Publish sync-release-metadata failed (run 32532695440/job 96928366087) with ratchet_core_window --allow-transitive-lock-refresh exit 3 "uv.lock package asttokens changed fields outside version, sdist, or wheels". PR smoke also red: release-core-floor-smoke FAILURE run 32532918668/job 96928367962 — sase_core_rs 0.29.6 missing authenticate_finalizer_plan and validate_finalizer_plan after 6639a2801. PyPI sase-core-rs 0.29.9 exports both; 0.29.6 does not. sase-telegram#19 MERGED. Proposing a child tale to restore those two gates; will not merge.

[2026-08-21T23:31:27Z · sase-ry.2--2] Progress: landed 2647b717a fix(release): let Publish ratchet the 0.29.9 core floor on master. Reproduced Publish on origin/release-please--branches--master with uv 0.12.5 / CPython 3.12: asttokens keys stayed name/version/source/sdist/wheels (no extra-field rewrite locally), but uv.lock package sase moved 0.16.0 -> 0.17.0 to match release-please pyproject, which the old expected-project-package check also refuses. Live CI still reported asttokens fields outside version/sdist/wheels (run 32532695440). Validator now treats dependencies, optional-dependencies, and source as refreshable for unchanged-set transitive PyPI packages; project package version may follow pyproject; core still version/sdist/wheels only; default mode still refuses any transitive change. Applied ratchet on master to sase-core-rs>=0.29.9,<0.30.0. 3.12 venv sase-core-rs==0.29.9: tools/check_sase_core_rs_bindings reports 368/368 including authenticate_finalizer_plan and validate_finalizer_plan; tools/validate_sase_core_rs exit 0. Will not merge. Next: wait for Publish sync-release-metadata on 2647b717a and release-core-floor-smoke on #284, then ci_watch submit.

[2026-08-21T23:31:45Z · sase-ry.2--2] PROPOSED FOLLOW-UP: just check lint (feature flags) errors on live flag bead sase-ro (key pluggable_finalizers) with no registry definition after the 24h orphan grace; the definition was retired (tests/test_finalizers_retirement.py) but the flag bead is still open. Unrelated to this tale; blocks just check on this tree.

## Dependencies

- **Depends on:** [sase-ry.1](sase-ry.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-ry.3](sase-ry.3.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ry.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ry.2.md) | [sase-ry.2](sase-ry.2.md) | 0 |
| [bbugyi200.athena.sase-ry.2--2--code](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ry.2--2--code/README.md) | [sase-ry.2](sase-ry.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2647b71`](https://github.com/sase-org/sase/commit/2647b717a48d387d45092b3fe27172f598f76aa8) | fix(release): let Publish ratchet the 0.29.9 core floor | [sase-ry.2](sase-ry.2.md) | 2026-08-21 23:29:04 UTC |
| sase | [`959a547`](https://github.com/sase-org/sase/commit/959a547709e7ed6a400494ed57a2009749ad4cdb) | test(release): keep ledger invariants off the core-floor contract set | [sase-ry.2](sase-ry.2.md) | 2026-08-21 23:44:58 UTC |
