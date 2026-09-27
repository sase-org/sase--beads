# Bead: sase-1aq.10.7.5.2 — Make exact remote stop and retry settle certainly

[Bead Pages](../README.md) / [sase-1aq.10.7.5](sase-1aq.10.7.5.md) / sase-1aq.10.7.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.land.md) · **Assignee:** `sase-1aq.10.7.5.2` · **Size:** large
**Created:** 2026-09-26 21:57:11 EDT · **Closed:** 2026-09-26 22:51:45 EDT
**Plan:** [202609/1aq\_close\_original\_gates.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_close_original_gates.md)

## Description

exact_ops_receipts: resolve the uncertain-receipt, catalog-lag, and killed-row reaping issues recorded on sase-xe.16.11 so exact remote operations meet acceptance.

## Notes

[2026-09-27T02:51:45Z · sase-1aq.10.7.5.2] exact_ops_receipts landed: settled-receipt same-key poll (fleet_mutate early return + client acceptance-window poll), index-backed catalog/detail merge for fresh launches, and no-dismiss fleet stop retaining retry/fork. Checks: sase-core just fast pass; gateway focused tests pass (fleet_mutate_same_key_returns_settled_after_terminal, fleet_catalog_overlay_serves_fresh_launch_before_rebuild, fleet_stop_retains_row_with_retry_and_fork, plus existing mutate suite); sase pytest tests/test_dispatch_mutations.py 9 passed, mobile retain threading pass. PROPOSED FOLLOW-UP: sase-core just check fails on clean-base clippy (nonminimal_bool in maintenance/fleet_owner_facts/tool_run, manual_range_contains in provider_usage) with rust-1.95; sase just check times out rebuilding sase-core-rs from dirty linked checkout; tests/test_kill_named_agent_dismiss.py fails on clean base with agent_scan wire schema mismatch (got 9, expected 10).

## Dependencies

- **Blocks:** [sase-1aq.10.7.5.3](sase-1aq.10.7.5.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.2.md) | [sase-1aq.10.7.5.2](sase-1aq.10.7.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`700b37b`](https://github.com/sase-org/sase/commit/700b37b3849e84cd775405b7279fdaef2ea8a3ef) | feat(dispatch): settle exact stop and retry receipts certainly | [sase-1aq.10.7.5.2](sase-1aq.10.7.5.2.md) | 2026-09-26 22:54:01 EDT |
