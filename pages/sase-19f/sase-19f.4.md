# Bead: sase-19f.4 — TUI and CLI display plus capacity editing surfaces

[Bead Pages](../README.md) / [sase-19f](README.md) / sase-19f.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1o.md) · **Assignee:** `sase-19f.4` · **Size:** medium
**Created:** 2026-09-25 12:24:40 EDT · **Closed:** 2026-09-25 19:43:08 EDT
**Plan:** [202609/queue\_capacity\_multiplier.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_multiplier.md)

## Description

sase-surfaces: render multiplier capacities as `c1.5x` badges with resolved units in the TUI detail, wait lane, and queue ladder, and expose them in agent-list JSON. The wait modal and the agent directive edit commands accept `<M>x` and keep it when other queue fields are edited.

## Notes

[2026-09-25T23:43:08Z · sase-19f.4] Rendered multiplier capacities as c1.5x badges with over-limit style when M>1, header '1.5x budget (7.5 capacity units)', wait-lane 'capacity budget 1.5x (7.5)', and queue-ladder c1.5x. Wait modal and directive edit accept <M>x, prefill 1.5x, persist multiplier while clearing integer (and vice versa), and keep 1.5x when only priority/weight is rewritten. Agent-list JSON exposes queue_capacity_multiplier. Focused tests for those surfaces passed (11). sase bead epic-symbols sase-19f.4 reported no leftovers.

## Dependencies

- **Depends on:** [sase-19f.3](sase-19f.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.4.md) | [sase-19f.4](sase-19f.4.md) | 0 |
