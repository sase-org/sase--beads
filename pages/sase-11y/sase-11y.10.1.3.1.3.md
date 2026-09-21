# Bead: sase-11y.10.1.3.1.3 — Route the post-update restart through the scheduler service proc

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.3` · **Size:** medium
**Created:** 2026-09-20 21:17:58 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

update-restart: make `restart_after_update` call `restart_service_proc("scheduler", ...)`, rename the axe-shaped injection types, drop the AXE-only `pid` / `attempts` / `verified` fields from `RestartInfo`, and update every `sase update`, `sase flag`, and `sase plugin` caller.

## Dependencies

- **Blocks:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.3/README.md) | [sase-11y.10.1.3.1.3](sase-11y.10.1.3.1.3.md) | 0 |
