# Bead: sase-xe.16.11.7.3 — Worker TLS trust, per-host continuation, and real fault proofs

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hv.md) · **Assignee:** `sase-xe.16.11.7.3` · **Size:** medium
**Created:** 2026-09-09 15:49:28 EDT · **Closed:** 2026-09-09 19:02:24 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

## Description

trust-fencing: apply validated TLS trust in the federation worker, thread per-host cursors through fan-out, and prove healthy-host survival and exact-instance fencing on real paths.

## Notes

[2026-09-09T23:02:24Z · sase-xe.16.11.7.3] Verified worker TLS trust, per-host catalog continuation, and exact-instance fencing with cargo test -p sase_gateway federation_worker::imp::tests --lib; cargo test -p sase_gateway fleet_mutate_refuses_stale_revision_and_superseded_instance --lib; uv run pytest tests/test_dispatch_federation.py::test_facade_catalog_hosts_threads_per_host_queries tests/ace/tui/test_fleet_agents.py::test_catalog_next_cursors_by_host_keeps_continuations_separate tests/ace/tui/test_fleet_agents.py::test_merge_catalog_pages_keeps_authoritative_counts_and_second_page_rows tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_fleet_catalog_refresh_requests_legal_pages_and_logical_keys; just check. Required epic-symbols check reported no entries.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.1](sase-xe.16.11.7.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.5](sase-xe.16.11.7.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.3/README.md) | [sase-xe.16.11.7.3](sase-xe.16.11.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dacce95`](https://github.com/sase-org/sase/commit/dacce95f3b441832bfe5d32544907652b75b57ef) | fix(fleet): continue catalog pages per host | [sase-xe.16.11.7.3](sase-xe.16.11.7.3.md) | 2026-09-09 20:07:44 EDT |
