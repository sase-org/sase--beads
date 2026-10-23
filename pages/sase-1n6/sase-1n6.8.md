# Bead: sase-1n6.8 — Release-green record and release metrics

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.8` · **Size:** medium
**Created:** 2026-10-19 16:40:09 EDT · **Closed:** 2026-10-20 13:41:41 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Previously Closed

> ↺ Closed 2026-10-20T16:51:52Z · done
>
> (none)
>
> Reopened 2026-10-20T17:05:42Z by `sase bead open`

## Description

metrics: a read-only tools/release_metrics derives release-green per SHA and the release figures, each with numerator, denominator and window, and publishes a pre-train baseline.

## Notes

[2026-10-20T16:50:50Z · sase-1n6.8] PRE-TRAIN BASELINE: release_metrics observed 2026-10-20T16:47:15Z over 2026-09-22T16:47:15Z to 2026-10-20T16:47:15Z (28 days). Days since last confirmed release: 1.23 days (106,662.49 seconds / 86,400). Landing to PyPI: p50 439.68 hours, p90 597.94 hours (1,551 samples). Time to release-green: n/a (0 completed observations; target <6h). Core lag: 575.31 hours (2,071,119.80 seconds / 3,600); includes one pin GitHub could not resolve, conservatively counted as uncontained. Burned versions: 0 of 4 weeks (0.00/week). Change-fail rate: n/a (0 of 0 eligible releases; no release had reached the 7-day maturity window).

[2026-10-20T16:50:57Z · sase-1n6.8] PROPOSED FOLLOW-UP: Fix the pre-existing contract manifest mismatch tracked by sase-iu: clean base has 84 manifest entries but marker selection discovers 87, so test_contract_manifest_matches_marker_selection and the 84-entry budget check fail.

[2026-10-20T16:51:52Z · sase-1n6.8] Implemented read-only release metrics and exact-SHA release-green evidence. Verified 10 focused tests, Ruff, live report and green CLI; recorded the 28-day baseline and the existing sase-iu contract-manifest follow-up. epic-symbols reported no leftovers. The prior full check had only the reproduced clean-base contract-manifest mismatch.

[2026-10-20T17:28:35Z · sase-1n6.8] PRE-TRAIN BASELINE (refreshed): release_metrics observed 2026-10-20T17:25:02.954837Z over 2026-09-22T17:25:02.954837Z to 2026-10-20T17:25:02.954837Z (28 days). Days since last confirmed release: 1.26 days (108930.384946 of 86400). Landing to PyPI: p50 437.81 hours, p90 597.44 hours (1546 samples). Time to release-green: n/a (0 of 0; target <6h). Core lag: 575.60 hours (2072147.7352230006 of 3600). Burned versions: 0 of 4 weeks (0.00/week). Change-fail rate: n/a (0 of 0 eligible releases). Every figure printed with numerator and denominator.

[2026-10-20T17:41:41Z · sase-1n6.8] Verified 11 fixture tests (exact-SHA green, known denominators, n/a empty samples, core-lag, pypi history, commit-range, job retry, tag timestamps, tool-path presence), live 28-day report with every figure's numerator/denominator (observed 2026-10-20T17:25:02Z), sase tool run check 131f8cbe85f9336990ec6ef5c47313c8 green, and no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-1n6.7](sase-1n6.7.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.9](sase-1n6.9.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.8/README.md) | [sase-1n6.8](sase-1n6.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b15cc3f`](https://github.com/sase-org/sase/commit/b15cc3fb5b56156729f0264cdd172e4274f771dd) | feat(release): add read-only release\_metrics and exact-SHA green evidence | [sase-1n6.8](sase-1n6.8.md) | 2026-10-20 13:42:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: E2 status | 1 |
| read-by | [agent:sase-1n6.8][2] | Need the phase scope and design file | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.8/README.md

<!-- sase:referenced-by:end -->
