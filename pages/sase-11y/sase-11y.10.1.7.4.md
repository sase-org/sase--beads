# Bead: sase-11y.10.1.7.4 — Retire the Services-tab fields the flag removal emptied

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.4` · **Size:** medium
**Created:** 2026-09-21 03:59:16 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

tui-dead-state: delete `AxeCollectedData.axe_status` / `axe_metrics`, the app's `_axe_status` / `_axe_metrics`, the `status` / `full_cycles` parameters they feed, and the `None` arm of `KeybindingFooter.set_service_health`, keeping the render pixel-identical.

## Dependencies

- **Blocks:** [sase-11y.10.1.7.6](sase-11y.10.1.7.6.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.4/README.md) | [sase-11y.10.1.7.4](sase-11y.10.1.7.4.md) | 0 |
