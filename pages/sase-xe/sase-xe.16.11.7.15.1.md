# Bead: sase-xe.16.11.7.15.1 — Host chips on remote nodes, never a here chip

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.1` · **Size:** small
**Created:** 2026-09-13 18:38:01 EDT · **Closed:** 2026-09-13 20:00:31 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

no-here-chip: invert the machine-chip policy — delete the here fallback so local rows never carry a chip, render the host alias chip on remote agent nodes in every grouping mode, and update render-cache keys, tests, and fleet PNG snapshots.

## Notes

[2026-09-14T00:00:31Z · sase-xe.16.11.7.15.1] Inverted machine-chip policy: local rows never render a here chip; remote agent/family/clan nodes keep the host-alias chip in every grouping mode including BY_MACHINE; indented member shells do not repeat it. Deleted the unreachable show_fleet_badge/star path. Verified unit tests (status indicators, grouping gutters, render-cache keys, BY_MACHINE in-place patch), refreshed fleet PNG goldens (no here chip on local visual-plan/code/review; apollo/mac chips on remote rows), and just check green. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.15.6](sase-xe.16.11.7.15.6.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.15.1/README.md) | [sase-xe.16.11.7.15.1](sase-xe.16.11.7.15.1.md) | 0 |
