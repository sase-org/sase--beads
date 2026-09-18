# Bead: sase-12p.3 — On-host verification of panel stability and stale-code surfacing

[Bead Pages](../README.md) / [sase-12p](README.md) / sase-12p.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mq.md) · **Assignee:** `sase-12p.3` · **Size:** medium
**Created:** 2026-09-18 06:26:41 EDT
**Plan:** [202609/by\_status\_panels\_and\_stale\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202609/by_status_panels_and_stale_tui.md)

## Description

verify-on-athena: restart the athena TUI onto the fixed tree, soak under BY_STATUS grouping with live churn proving `@epic` stays mounted with no steady-state unsupported_grouping fallbacks, script a checkout-advance to prove the staleness indicator fires and clears through a restart, and add a regression guard against silent full-rebuild reintroduction.

## Dependencies

- **Depends on:** [sase-12p.1](sase-12p.1.md) ◐ · ⧖ 2026-09-18
- **Depends on:** [sase-12p.2](sase-12p.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12p.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12p.3/README.md) | [sase-12p.3](sase-12p.3.md) | 0 |
