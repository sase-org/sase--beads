# Bead: sase-ns.6.1 — Retire a fixed node's historical flake evidence

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.land.md) · **Assignee:** `sase-ns.6.1` · **Size:** large
**Created:** 2026-08-16 21:02:34 EDT
**Plan:** [202608/task\_backlog\_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)

## Description

flake_gate_retirement: task bead sase-nv. Let the reproducible-flake gate retire historical failure evidence for a node that has since been fixed, so `just check-full`'s last gate stops being a permanent red.

## Notes

[2026-08-17T01:40:24Z · sase-ns.6.1] PROPOSED FOLLOW-UP: `sase init memory --check` fails on a clean master checkout (verified via git stash, no relation to this phase's diff) — memory README/AGENTS.md/provider shims are out of sync in the chezmoi-linked repo, blocking just check's SASE validation step (and therefore its scoped test lane) for every agent in this workspace.

[2026-08-17T01:40:46Z · sase-ns.6.1] PROPOSED FOLLOW-UP: the live durable flake store (~/.sase/test-selection/gh_sase-org__sase/, shared across concurrent agents on this host) has accumulated two new reproducible flakes unrelated to this phase and not previously named in the bead/plan: tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls and tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor. Neither is retired or added to the baseline by this phase (out of scope); each needs its own filed bead before it can be added as baseline debt.

[2026-08-17T01:45:21Z · sase-ns.6.1] PROPOSED FOLLOW-UP: a third reproducible flake unrelated to this phase has since appeared in the shared durable store: tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error. Confirmed via the empty-nodeid-baseline re-run (see close note). Needs its own filed bead before it can be added as baseline debt.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.1.md) | [sase-ns.6.1](sase-ns.6.1.md) | 0 |
