# Bead: sase-11y.10.1.7.4 — Retire the Services-tab fields the flag removal emptied

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.4` · **Size:** medium
**Created:** 2026-09-21 03:59:16 EDT · **Closed:** 2026-09-21 04:43:55 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

tui-dead-state: delete `AxeCollectedData.axe_status` / `axe_metrics`, the app's `_axe_status` / `_axe_metrics`, the `status` / `full_cycles` parameters they feed, and the `None` arm of `KeybindingFooter.set_service_health`, keeping the render pixel-identical.

## Notes

[2026-09-21T08:43:55Z · sase-11y.10.1.7.4] Retired Services-tab dead state: deleted AxeCollectedData.axe_status/axe_metrics, app _axe_status/_axe_metrics, status/full_cycles params through AxeDashboard+AxeStatusSection, and the None arm of KeybindingFooter.set_service_health (now ServiceHealth-only; initial None kept as pre-snapshot pill). Render pixel-identical: fix-tui-screenshots updated=0 with no golden changes, plus new placeholder regression test. Focused suites pass (58+54); sase tool run check green except the pre-existing sase-14j symvision pair, left per plan. The 2 visual failures are pre-existing on pristine tree and already tracked by sase-155/sase-151.

## Dependencies

- **Blocks:** [sase-11y.10.1.7.6](sase-11y.10.1.7.6.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.4/README.md) | [sase-11y.10.1.7.4](sase-11y.10.1.7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3fbe914`](https://github.com/sase-org/sase/commit/3fbe914fb1a920af5f2cfa3fc3b1b7053b5c8f5f) | refactor(services-tab): retire flag-emptied TUI dead state | [sase-11y.10.1.7.4](sase-11y.10.1.7.4.md) | 2026-09-21 04:46:22 EDT |
