# Bead: sase-zl.13.8 — Apply checkpoint projections and provider-aware budgets

[Bead Pages](../README.md) / [sase-zl.13](sase-zl.13.md) / sase-zl.13.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zl.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zl.land.md) · **Assignee:** `sase-zl.13.8` · **Size:** medium
**Created:** 2026-09-11 23:43:33 EDT · **Closed:** 2026-09-12 13:33:35 EDT
**Plan:** [202609/monitor\_continuation\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_continuation_landing_repairs.md)

## Description

budgets: select and render safe checkpoint reductions, use actual provider and transport limits, and publish recoverable refusals through delivery state.

## Notes

[2026-09-12T17:33:35Z · sase-zl.13.8] Implemented continuation budget prompt projection/provider transport defaults/delivery refusal state; added schema/defaults/tests and queue-capacity compatibility for current core. Verified focused continuation/provider tests (34 passed), focused queue/capacity tests (219 passed plus standalone bead capacity samples), and just check (full-suite escalation) passed.

## Dependencies

- **Depends on:** [sase-zl.13.2](sase-zl.13.2.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zl.13.3](sase-zl.13.3.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zl.13.6](sase-zl.13.6.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zl.13.9](sase-zl.13.9.md) ✓ · ⧖ 2026-09-11

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2eb5205`](https://github.com/sase-org/sase/commit/2eb520541192cf6964a0de898627eacdf2f233bb) | feat: Apply checkpoint projections and provider-aware budgets (sase-zl.13.8) | [sase-zl.13.8](sase-zl.13.8.md) | 2026-09-12 13:40:18 EDT |
