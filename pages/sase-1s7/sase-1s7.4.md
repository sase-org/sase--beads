# Bead: sase-1s7.4 — An accepted release.yml rehearsal on the refreshed release PR branch

[Bead Pages](../README.md) / [sase-1s7](README.md) / sase-1s7.4

**Status:** ✓ closed · **Resolution:** canceled · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1b0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1b0.md) · **Assignee:** `sase-1s7.4` · **Size:** small
**Created:** 2026-11-10 14:38:16 EST · **Closed:** 2026-11-10 17:22:43 EST
**Plan:** [202611/ci\_green\_v0\_19\_0\_pypi\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/ci_green_v0_19_0_pypi_release.md)

## Description

rehearse: refresh the release-please branch onto the fixed master, dispatch one rehearse-mode release.yml run there, and accept it job by job (or skip per the rehearsal decision).

## Notes

[2026-11-10T20:37:19Z · sase-1s7.4] Rehearsal dispatched: release.yml run https://github.com/sase-org/sase/actions/runs/42896552147 (mode=rehearse) at release-please--branches--master e9237c1c5219b64ac1ed30a0a69e275a8ecec24a. Branch refreshed via publish.yml run https://github.com/sase-org/sase/actions/runs/42895808739 which picked up master-reds fix 1df3ade04d. release_watch --once shows primary core_incompatible (no ambiguous_trains), so rehearsal proceeds per plan.

[2026-11-10T20:41:04Z · sase-1s7.4] Attempt 1 (run 42896552147 at e9237c1c52) failed at build containment: REFUSED CORE_LAG(pin=5c0e49cf, core=0.43.2). Root cause was a mid-refresh race, not a product defect: I dispatched while publish.yml run 42895808739 was still running. e9237c1c52 carried the master-reds fix but still pinned sase-core-rs==0.43.2; the publish sync-metadata job then pushed 37dfdbc59c bumping the pin to 0.44.2. Local containment proof passes for 0.44.2+5c0e49cf (tag v0.44.2 = 1ba79d2f). Dispatched attempt 2 (of max 2) as run 42897628895 at 37dfdbc59c.

[2026-11-10T20:44:59Z · sase-1s7.4] Attempt 2 (run 42897628895 at 37dfdbc59c, pins sase-core-rs==0.44.2 + rev 5c0e49cf) is IN FLIGHT and healthy past the attempt-1 failure point: identity/build/qualify-prepare green, build step 9 containment success, all 4 exercise-legs green, qualify-ci/prepare green, stash skipped (rehearse mode). Still running: merged exercise verdict, qualify-ci/build-core (lint+test), then qualify + publish. Lane blocked: staged monitor q8xe32pypsxq (watch attempt-1 run 42896552147) never launched and holds the sase-1s7.4 monitor lane; sase monitor stop refuses staged monitors, so no new watch could be staged. NEXT: judge 42897628895 job-by-job per plan; attempt 2 of max 2 already dispatched, so a stale q8xe32 follow-up MUST NOT dispatch again — judge-only. Then notes to sase-1q2.9.3 + sase-1oe.4, epic-symbols, close.

[2026-11-10T20:49:48Z · sase-1s7.4--1] Stale monitor q8xe32 completed (attempt-1 failure already judged); attempt-2 run 42897628895 at 37dfdbc59c still in_progress (identity/build/qualify-prepare/exercise-legs+merged verdict green, qualify-ci/build-core running). Staging fresh watch for attempt-2; judge-only, no further dispatches.

[2026-11-10T22:20:38Z · sase-1s7.4--2] Attempt-2 rehearse run judged FAILURE: https://github.com/sase-org/sase/actions/runs/42897628895 (mode=rehearse, release-please--branches--master @ 37dfdbc59c). Per-criterion verdicts: identity SUCCESS; build SUCCESS (step 9 containment success, sase-core-rs 0.44.2 + pin 5c0e49cf); qualify-prepare SUCCESS; exercise 4/4 legs SUCCESS (macos+ubuntu x wheel+sdist) + merged verdict SUCCESS (N-1 upgrade path intact); qualify-ci prepare/build-core/tests(3.12,3.13,3.14)/perf-floors/tutorial-tests/ace-page-group-isolation SUCCESS; visual-test FAILURE (advisory per plan, not acceptance); lint FAILURE (BLOCKING — fmt-docs-check: docs/overrides/generated/release_announce.html stale for manifest 0.19.0); qualify FAILURE (verdict cascade); publish FAILURE (promotion predicate: uv not found + red qualification); stash/confirm/confirm-install SKIPPED as expected in rehearse mode. Master checkout is clean: pyproject 0.18.1 matches generated file stamp 0.18.1, so staleness is release-branch-only (release-please bumped manifest without regenerating), not a base-tree reproduction.

[2026-11-10T22:22:07Z · sase-1s7.4--2] PROPOSED FOLLOW-UP: release-please version bump leaves docs/overrides/generated/release_announce.html stale (manifest 0.19.0 vs generated stamp), failing blocking lint fmt-docs-check on the release branch; fix generation/refresh in the release flow on master, refresh branch via bare publish.yml run, and re-rehearse release.yml with a fresh dispatch budget (attempts 1-2 exhausted: runs 42896552147, 42897628895)

[2026-11-10T22:22:13Z · sase-1s7.4--2] PROPOSED FOLLOW-UP: advisory visual-test red on rehearse run 42897628895 — tool_runs_card_failed_120x40 golden drift 32805/1520532 px (2.157%); per plan advisory only, never acceptance; triage golden vs renderer change separately

[2026-11-10T22:22:43Z · sase-1s7.4--2] Rehearse run 42897628895 FAILURE, no dispatches remain (2/2 used). Blocking red: qualify-ci/lint step "Check generated model docs" — fmt-docs-check: docs/overrides/generated/release_announce.html stale for manifest 0.19.0 (release-branch-only; master 0.18.1 in sync). Cascaded: qualify verdict + publish promotion predicate red. Green: identity/build/containment/qualify-prepare, 4/4 exercise legs + merged verdict, tests, perf-floors, tutorial-tests, ace-page-group-isolation; stash/confirm/confirm-install skipped per rehearse mode. Advisory visual-test drift filed as PROPOSED FOLLOW-UP. Next: master-side release-flow fix + refresh + re-rehearse under a new budget.

## Dependencies

- **Depends on:** [sase-1s7.1](sase-1s7.1.md) ✓ · ⧖ 2026-11-10
- **Blocks:** [sase-1s7.6](sase-1s7.6.md) ◐ · ⧖ 2026-11-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1s7.4.md) | [sase-1s7.4](sase-1s7.4.md) | 0 |
