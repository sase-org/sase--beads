# Bead: sase-11y.2.1.3 — Restart decisions and the locked service state store

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.3` · **Size:** medium
**Created:** 2026-09-16 15:15:28 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

restart-state: add the pure `decide_service_restart` function (restart policy, clean-exit rules, orchestrator-identical backoff and crash-loop accounting) and the flock-guarded `~/.sase/service/state.json` store (machine-local enablement overrides, boot-id-keyed stops, markers, host record) with bindings, plus the Python restart, state, paths, and boot-id facades.

## Dependencies

- **Depends on:** [sase-11y.2.1.2](sase-11y.2.1.2.md) ◐ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.2.1.4](sase-11y.2.1.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.3/README.md) | [sase-11y.2.1.3](sase-11y.2.1.3.md) | 0 |
