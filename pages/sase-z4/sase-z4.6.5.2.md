# Bead: sase-z4.6.5.2 — Add the missing integrated weighted workload acceptance

[Bead Pages](../README.md) / [sase-z4.6.5](sase-z4.6.5.md) / sase-z4.6.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.land.md) · **Assignee:** `sase-z4.6.5.2` · **Size:** medium
**Created:** 2026-09-10 13:23:42 EDT · **Closed:** 2026-09-10 16:31:09 EDT
**Plan:** [202609/weighted\_capacity\_final\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_final_acceptance.md)

## Description

integrated-acceptance: exercise weighted claims, parallel-lineage handoffs, monitor transfer, research swarm expansion, cleanup, and runtime/CLI/TUI parity through real lifecycle fixtures rather than isolated projections.

## Notes

[2026-09-10T20:30:17Z · sase-z4.6.5.2] PROPOSED FOLLOW-UP: Restore feature-flag lint gate — just check currently fails because live flag bead sase-z0 has no registry definition for key link_events.

[2026-09-10T20:30:19Z · sase-z4.6.5.2] PROPOSED FOLLOW-UP: Clean stale symvision epic symbols — just _lint-symvision currently fails because Justfile still whitelists UsagePeekSnapshot, cached_usage_display_snapshot, and cached_usage_indicator_projection under closed bead sase-z7.3.

[2026-09-10T20:31:09Z · sase-z4.6.5.2] Added weighted fakey acceptance for fractional fill, explicit zero runner/priority, installed research_swarm typed planning, and lifecycle fill. Verified: tests/fakey/test_runner_slots_e2e.py -q (11 passed), focused queue/lineage/CLI/TUI pytest set (136 passed), just fmt, epic-symbols none. just check is blocked by unrelated pre-existing feature-flag/symvision gates; follow-up notes recorded.

## Dependencies

- **Depends on:** [sase-z4.6.5.1](sase-z4.6.5.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.5.3](sase-z4.6.5.3.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.2/README.md) | [sase-z4.6.5.2](sase-z4.6.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`788c63e`](https://github.com/sase-org/sase/commit/788c63e286604dbdda92ad476750fe02be9abc9f) | test(runner-slots): add integrated weighted fakey acceptance | [sase-z4.6.5.2](sase-z4.6.5.2.md) | 2026-09-10 16:32:28 EDT |
