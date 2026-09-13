# Bead: sase-zu.6 — Refreshes stop re-paying for history the session already has

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.6` · **Size:** medium
**Created:** 2026-09-12 10:35:49 EDT · **Closed:** 2026-09-13 06:13:41 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

refresh_reuse: make the full-history upgrade a once-per-committed-query event so ordinary auto-refreshes use the delta path instead of repeating the expensive load.

## Notes

[2026-09-13T10:13:41Z · sase-zu.6] Implemented query-keyed full-history reuse for Agents refreshes; verified targeted pytest for lazy Tier 2/query-window behavior, adjacent refresh/revalidate/coalescing tests, clean epic-symbols for sase-zu.6, and just check.

## Dependencies

- **Depends on:** [sase-zu.2](sase-zu.2.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zu.4](sase-zu.4.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.7](sase-zu.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.6/README.md) | [sase-zu.6](sase-zu.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e08f08`](https://github.com/sase-org/sase/commit/2e08f0842d0be3c7526807e29b2c98d5be5509a8) | fix(agents): reuse full-history refreshes by query | [sase-zu.6](sase-zu.6.md) | 2026-09-13 06:49:43 EDT |
