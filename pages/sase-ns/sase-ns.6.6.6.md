# Bead: sase-ns.6.6.6 — Task backlog top five - clear the two red verification gates and the three reproducible test hazards behind them

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.land`
**Created:** 2026-08-17 05:54:38 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

The reproducible-flake gate has no non-epic-owned node holding it red, the serial ACE PNG visual lane is green on master, the last known fork-after-threads hazard in the test suite is gone, and an agent typing a bare `sase` can no longer be silently answered by a different checkout's build. Task beads sase-mv, sase-ny, sase-lk, sase-o5, and sase-o6 are closed on evidence.

## Notes

[2026-08-17T13:29:58Z · 04l--2] DISCOVERED ISSUE: just selection-health --fail-on-new-flake is still red after just test-cost 31946 passed / 10 skipped (monitor 9mp1g9hehqgv) while verifying monitor_node_under_starter. The gate names 3 nodes exceeding tests/reproducible_flake_baseline.txt (records after 2026-08-15T17:22:27Z): tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error (ready sase-ob, +1), tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config (in-progress sase-mv, +1), and tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo (new ready task sase-oh). None are caused by the Agents-tab nesting change. This epic's flake-baseline exit criterion still has these three live holdouts.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.6.land/README.md) | [sase-ns.6.6.6](sase-ns.6.6.6.md) | 0 |
