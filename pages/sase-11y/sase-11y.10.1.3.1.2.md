# Bead: sase-11y.10.1.3.1.2 — Delete the axe-start systemd scope wrapper and its evidence

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.2` · **Size:** medium
**Created:** 2026-09-20 21:17:57 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

systemd-scope: delete `sase/axe/systemd_scope.py`, the `_allow_systemd_scope` wrapping and unwrapped-retry branch in `_process_start.py`, the `axe.systemd_scope` doctor check, and the `orchestrator_session_scope` issue the status collector appends.

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.1](sase-11y.10.1.3.1.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.2/README.md) | [sase-11y.10.1.3.1.2](sase-11y.10.1.3.1.2.md) | 0 |
