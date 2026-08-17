# Bead: sase-ns.6.6.1 — Retire already-fixed nodes from the flake-baseline gate (sase-o0)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.1` · **Size:** medium
**Created:** 2026-08-17 04:03:10 EDT · **Closed:** 2026-08-17 04:13:38 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

flake_retire: declare `# fixed-at:` retirement in tests/reproducible_flake_baseline.txt for every currently-reported node whose fix commit can be named, starting with the proven test_override_pills_keep_narrow_top_bar_in_bounds case, and audit the three remaining unexplained nodes without declaring any node that cannot be tied to a named fix commit.

## Notes

[2026-08-17T08:13:38Z · sase-ns.6.6.1] Added fixed-at retirements in tests/reproducible_flake_baseline.txt for top-bar 981106799, query-profile 5d0bcf9e8, var schema skew 57c71d17a, and bead stats golden 278cc810b. Verified just install passed; just selection-health --fail-on-new-flake dropped from 7 exceeding nodes to 3 remaining out-of-scope nodes (sase-n4 usage-limit plus this epic's monitor_idle_bound and approval_anchor phases); git diff --check passed; just check passed.

[2026-08-17T08:14:53Z · sase-ns.6.6.1] Verified just install, just selection-health --fail-on-new-flake, git diff --check, and just check; baseline retirements leave only three out-of-scope exceeding nodes.

## Dependencies

- **Blocks:** [sase-ns.6.6.4](sase-ns.6.6.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-ns.6.6.5](sase-ns.6.6.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.1/README.md) | [sase-ns.6.6.1](sase-ns.6.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`72d3d5c`](https://github.com/sase-org/sase/commit/72d3d5c9f352dbc3fdfc5ee520313ef5085815ad) | test: retire fixed reproducible flake nodes | [sase-ns.6.6.1](sase-ns.6.6.1.md) | 2026-08-17 04:15:38 EDT |
