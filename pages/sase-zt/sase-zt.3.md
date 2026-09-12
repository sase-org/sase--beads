# Bead: sase-zt.3 — The capacity badge and the live/authored split

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.3` · **Size:** medium
**Created:** 2026-09-12 10:33:30 EDT · **Closed:** 2026-09-12 17:24:50 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

display: add the `cN` capacity badge to agent nodes and agent family nodes beside the existing weight badge, accent an over-subscribing budget, move the queue ladder and detail pane onto each waiter's own admission limit, and restate the wait and epic-approval modals.

## Notes

[2026-09-12T21:23:12Z · sase-zt.3] PROPOSED FOLLOW-UP: Fix artifact-index schema drift - after the linked core fast-forward, tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs expects schema 27 while rebuild writes 28.

[2026-09-12T21:23:14Z · sase-zt.3] PROPOSED FOLLOW-UP: Fix load-tiering oracle impossible-filter regression - tests/test_agent_load_tiering_harness.py::test_load_tiering_oracle_reports_under_selecting_candidate_filter reports 19 missing full-history rows under a provider filter that matches no candidates.

[2026-09-12T21:24:50Z · sase-zt.3] Implemented cN capacity badges, per-waiter admission-limit projection, queue ladder/detail free-capacity display, and capacity-budget wording for wait/approval UI with the legacy threshold display still behind queue_capacity_budget=false. Verified: just fmt; just _lint-symvision; focused pytest for agent-list runner status, queue section, runner-slot capacity, and capacity snapshot parity (34 passed); sase bead epic-symbols sase-zt.3 reported no entries. just check ran lint gates successfully but escalated to the full suite and failed two reproducible unrelated tests, recorded as PROPOSED FOLLOW-UP notes on this bead.

## Dependencies

- **Depends on:** [sase-zt.2](sase-zt.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zt.4](sase-zt.4.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zt.5](sase-zt.5.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.3/README.md) | [sase-zt.3](sase-zt.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c89591`](https://github.com/sase-org/sase/commit/3c89591db8b4e46108fa56dd501b00060aa70cc0) | feat(ace): show authored queue capacity budgets | [sase-zt.3](sase-zt.3.md) | 2026-09-12 17:26:47 EDT |
