# Bead: sase-1i5.6 — Guarantee a nonzero peak RSS for every recorded run (sase-1f0)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.6` · **Size:** medium
**Created:** 2026-10-08 09:47:20 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

demand-rss-flake: make the tree-RSS sampler record a real peak even for children that exit before the first sample, prove the node is stable under repetition and load, and close sase-1f0.

## Notes

[2026-10-08T14:05:10Z · sase-1i5.6] Mechanism confirmed: tree_rss_kib scans /proc; a child that exits before the only tree sample is a zombie whose stat RSS reads 0, so the sample counts (tree_rss_samples=1) with peak 0. Probed: zombie_scan=0 always; live python-child scan caught post-exit reads 0. wait4 ru_maxrss for true/python-c is 13376 KiB, a valid measured floor. Failing assert reproduced: tests/tool/test_demand_runs.py:261 assert 0 > 0.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.6/README.md) | [sase-1i5.6](sase-1i5.6.md) | 0 |
