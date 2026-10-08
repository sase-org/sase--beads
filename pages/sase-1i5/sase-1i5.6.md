# Bead: sase-1i5.6 — Guarantee a nonzero peak RSS for every recorded run (sase-1f0)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.6` · **Size:** medium
**Created:** 2026-10-08 09:47:20 EDT · **Closed:** 2026-10-08 10:48:01 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

demand-rss-flake: make the tree-RSS sampler record a real peak even for children that exit before the first sample, prove the node is stable under repetition and load, and close sase-1f0.

## Notes

[2026-10-08T14:05:10Z · sase-1i5.6] Mechanism confirmed: tree_rss_kib scans /proc; a child that exits before the only tree sample is a zombie whose stat RSS reads 0, so the sample counts (tree_rss_samples=1) with peak 0. Probed: zombie_scan=0 always; live python-child scan caught post-exit reads 0. wait4 ru_maxrss for true/python-c is 13376 KiB, a valid measured floor. Failing assert reproduced: tests/tool/test_demand_runs.py:261 assert 0 > 0.

[2026-10-08T14:47:31Z · sase-1i5.6] PROPOSED FOLLOW-UP: just check full-suite lane has 16 pre-existing failures unrelated to the RSS fix (bead fast-path x3, terminology x2, plan gates x3, macro groups x2, import budget, finalizers, gate detach, agent meta, plan archive, claimed status) — fail byte-identically on clean base (git stash) and patched tree; owned by other epics/phases, likely load-sensitive under host loadavg ~40.

[2026-10-08T14:48:01Z · sase-1i5.6] Verified: flaky node test_foreground_run_records_context_usage_and_grant passes 50/50 serial and 20/20 under 8-way parallel load (pre-fix ~50% fail rate on this host); full tests/tool/ 463 passed 1 skipped; new regression tests fail pre-fix, pass post-fix; sase-1f0 closed done; no epic-symbol leftovers; 16 unrelated full-suite failures reproduce byte-identically on clean base, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.6/README.md) | [sase-1i5.6](sase-1i5.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f01f87d`](https://github.com/sase-org/sase/commit/f01f87dddf2881583b243948b3358a9ff0950c2b) | fix(tool): floor demand tree RSS at reaped child ru\_maxrss | [sase-1i5.6](sase-1i5.6.md) | 2026-10-08 10:50:03 EDT |
