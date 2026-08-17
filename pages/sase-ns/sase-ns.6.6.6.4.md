# Bead: sase-ns.6.6.6.4 — Replace the last known fork-after-threads lock holders in the test suite

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.4` · **Size:** medium
**Created:** 2026-08-17 05:54:39 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

forksafe: replace the four multiprocessing fork sites in tests/test_sdd_git_contention.py with the in-process lock-holder seam that already fixed the identical hazard on tests/test_plan_approval_actions.py.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.6.4/README.md) | [sase-ns.6.6.6.4](sase-ns.6.6.6.4.md) | 0 |
