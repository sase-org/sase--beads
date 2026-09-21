# Bead: sase-11y.10.1.7.2 — Retire the AXE desired-state marker

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.2` · **Size:** medium
**Created:** 2026-09-21 03:59:14 EDT · **Closed:** 2026-09-21 04:45:30 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

desired-state: derive the scheduler's desired state from the service host instead of `~/.sase/axe/desired_state.json`, rebase the `axe.health` doctor check and the status collector on it, and delete the marker module, its `record_desired_state` plumbing, and its tests.

## Notes

[2026-09-21T08:45:30Z · sase-11y.10.1.7.2] Retired the AXE desired-state marker: new sase.axe._scheduler_desired_state derives AxeDesiredStateRecord(state, source='service host', timestamp) from the scheduler proc in persisted_or_current_status (stop marker wins; unknown/missing values yield None, host unreadable yields None); axe.health rebased on it (warns only when host wants scheduler running with no live orchestrator, next_steps point at sase service status / sase scheduler start, id axe.health and group axe kept, retitled Scheduler service proc health); status collector rebased; lifecycle journal stamps desired_state None (readers still tolerate old dict entries); deleted desired_state.py, record_desired_state/desired_state_source params, and the desired_state.json surface token; Rust wire shape unchanged. Verified: 53 focused tests pass (incl. new tests/test_axe_scheduler_desired_state.py), live host yields running/service-host record with healthy snapshot and OK doctor check, sase tool run check shows only the known sase-14j symvision pair, no linked-repo (sase-telegram, sase-core) consumers found, epic-symbols none.

## Dependencies

- **Depends on:** [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.2/README.md) | [sase-11y.10.1.7.2](sase-11y.10.1.7.2.md) | 0 |
