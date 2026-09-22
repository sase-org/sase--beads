# Bead: sase-168.2 — Gateway attention inventory must not fail on busy hosts

[Bead Pages](../README.md) / [sase-168](README.md) / sase-168.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pa.md) · **Assignee:** `sase-168.2` · **Size:** small
**Created:** 2026-09-22 10:05:58 EDT · **Closed:** 2026-09-22 10:18:05 EDT
**Plan:** [202609/remote\_attention\_dismissal\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_attention_dismissal_fix.md)

## Description

inventory-row-cap: in sase-core, drop the 200 raw-row cap from project_fleet_attention_inventory (paging bounds output) and pre-filter the gateway handler to actionable rows, with core and route tests.

## Notes

[2026-09-22T14:17:22Z · sase-168.2] PROPOSED FOLLOW-UP: follow inventory next_cursor per host so hosts with more than 100 pending requests are fully mirrored — detail: _payload_is_fresh_complete treats has_more pages as incomplete and the TUI fetches only the first page

[2026-09-22T14:17:50Z · sase-168.2] PROPOSED FOLLOW-UP: after a failed network read the federation worker cache-only reads should carry the stale status and error instead of reporting status ok — detail: stale snapshots currently look fresh once the network fails

[2026-09-22T14:18:05Z · sase-168.2] inventory-row-cap done: project_fleet_attention_inventory no longer subject to the 200 raw-row cap (new project_attention_entries helper; project_fleet_attention keeps its reject-201 contract), gateway inventory pre-filters to actionable rows. Verified: 29/29 sase_core fleet_attention tests pass (3 new), 16/16 sase_gateway fleet_attention tests pass (1 new busy-host route test), cargo clippy clean on both crates. sase_core_py check fails only on env Python 3.11 vs required abi3-py312, unrelated to this change. No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-168.3](sase-168.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-168.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-168.2/README.md) | [sase-168.2](sase-168.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@19ee7a0`](https://github.com/sase-org/sase-core/commit/19ee7a09fc0687daec0f336ae2798c96866486c1) | fix(fleet-attention): lift 200-row cap from attention inventory, pre-filter gateway rows | [sase-168.2](sase-168.2.md) | 2026-09-22 10:19:08 EDT |
