# Bead: sase-11y.10.1.7.2 — Retire the AXE desired-state marker

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.2` · **Size:** medium
**Created:** 2026-09-21 03:59:14 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

desired-state: derive the scheduler's desired state from the service host instead of `~/.sase/axe/desired_state.json`, rebase the `axe.health` doctor check and the status collector on it, and delete the marker module, its `record_desired_state` plumbing, and its tests.

## Dependencies

- **Depends on:** [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.2/README.md) | [sase-11y.10.1.7.2](sase-11y.10.1.7.2.md) | 0 |
