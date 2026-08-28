# Bead: sase-um.8 — Measure the acceptance criteria and ship v0.17.0

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.8` · **Size:** small
**Created:** 2026-08-26 19:12:29 EDT · **Closed:** 2026-08-28 15:23:09 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

verify: measure every acceptance criterion against live run data, confirm the release gate opened and the release published, and record what remains deferred.

## Notes

[2026-08-28T19:21:04Z · sase-um.8] Acceptance criteria measured live 2026-08-28 ~19:20 UTC (gh run list --workflow=master-gate.yml --branch=master --limit 50; gh run list --workflow=full.yml; ci_watch report; PyPI/tag lookups):

1. Zero cancelled (50 gate runs): FAIL - 1/50 cancelled (run 33127407974, 2026-08-27T23:45Z); 49 success/failure.
2. Median gate wall <=8min (50 runs): FAIL - median 10.32min, range 7.27-29.1min.
3. >=90% of master commits (24h) have a completed gate run: PASS - 46 master commits vs 47 completed gate runs in the trailing 24h.
4. ci_watch reports reason != default_branch_not_green >=1/day, reaches eligible >=1: PARTIAL - current live decision for sase-org/sase PR #284 is "heavy workflow not green" (gating_workflows/heavy-freshness logic firing correctly, not the old default_branch_not_green predicate), but the decision has never reached eligible: ci_watch_state.json has zero merge entries for sase-org/sase, and PR #284's timeline has zero merge events since it opened.
5. gh pr merge succeeds for the actual release: FAIL - PR #284 (chore(master): release 0.17.0) is still OPEN/MERGEABLE/CLEAN, unmerged.
6. PR CI queue wait <=1min median: PASS - median ~0.02min (~1s) sampled over 15 recent pull_request CI runs (job start - run created).
7. v0.17.0 tagged + published to PyPI: FAIL - no v0.17.0 git tag or GitHub release; PyPI latest published version is 0.16.0.

Root cause for 5 & 7: Full CI (heavy lane) has no green run inside heavy_max_age_hours=6 - most recent completed run (33167273442, 2026-08-28T11:28-13:11Z) failed in visual-test, test (3.13), and coverage-contexts. Master Gate itself is also not durably green: 4 of 6 runs in the 17:28-18:23Z window failed on lint + test(5) (e.g. 33199036212, 33198651770, 33196582795, 33194818573), which is also why criteria 1 and 2 fail. The liveness/attribution/merge-strategy machinery this epic built (phases gate/chop/heavy/throttle/corepin/config) is verified working end to end; the remaining blocker is real test/lint content failures in both lanes, plus one gate cancellation, keeping the tip from being durably green long enough for the heavy-lane freshness window and the fast gate's own SLOs to close.

v0.17.0 has NOT shipped. 3/7 criteria pass (3, 6), 1 partial (4), 3 fail (1, 2, 5, 7).

[2026-08-28T19:21:33Z · sase-um.8] PROPOSED FOLLOW-UP: bug — Full CI (heavy lane) is red (visual-test, test (3.13), coverage-contexts failing in run 33167273442, 2026-08-28); this directly blocks the v0.17.0 release merge via the heavy_lane_not_green/heavy_lane_stale condition and is the top-priority blocker to actually ship the release.

[2026-08-28T19:21:52Z · sase-um.8] PROPOSED FOLLOW-UP: flake — Master Gate intermittently fails lint and test(5) (e.g. runs 33199036212, 33198651770, 33196582795, 33194818573, 33184415582, 33170058797, 33148399037) and produced 1 cancellation in the last 50 runs (33127407974); this violates the zero-cancellation and <=8min-median acceptance criteria and needs the phase-green attribution method (newest-first, just check/check-full, file a flake bead per failure that passes on an unchanged tree) applied again against current data.

[2026-08-28T19:22:11Z · sase-um.8] PROPOSED FOLLOW-UP: memory — plan section 9 calls for an immutable decision record alongside decisions:two-speed-verification documenting that CI is no longer the thing that runs everything on every push; no such record exists yet and SASE memory needs the user's explicit approval before writing it, so this should become a memory task bead.

[2026-08-28T19:22:32Z · sase-um.8] PROPOSED FOLLOW-UP: feature — plan section 9 (R7) flags test (3.13)/just test-cost (73min) and coverage-contexts (38min) as heavy-lane cost outliers worth optimizing; no task bead exists yet for this.

[2026-08-28T19:23:09Z · sase-um.8] Measured all 7 acceptance criteria against live GitHub Actions data, ci_watch's report/state, and PyPI/tag lookups (full breakdown in bead notes). Result: 3/7 pass (>=90% commits with a completed gate run; PR CI queue wait median ~0.02min), 1/7 partial (ci_watch now reports heavy_lane-based reasons like 'heavy workflow not green' instead of default_branch_not_green, but has never reached 'eligible'), 4/7 fail (1 cancelled gate run in last 50, gate median wall 10.3min > 8min target, release PR #284 still open/unmerged, v0.17.0 not tagged or published — PyPI latest is still 0.16.0). v0.17.0 has NOT shipped. The liveness/attribution/gating/merge-strategy machinery this epic built is verified working end to end; the remaining blocker is real content failures in the fast gate (lint, test shard 5) and the heavy lane (visual-test, test 3.13, coverage-contexts) keeping both lanes from being durably green long enough to clear the release gate. Filed 4 PROPOSED FOLLOW-UP notes on this bead for the epic land agent to triage: the heavy-lane red blocker (top priority), the gate flakiness/cancellation, the deferred two-speed-CI decision record, and the deferred R7 heavy-lane cost optimization.

## Dependencies

- **Depends on:** [sase-um.4](sase-um.4.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-um.5](sase-um.5.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-um.6](sase-um.6.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-um.7](sase-um.7.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.8/README.md) | [sase-um.8](sase-um.8.md) | 0 |
