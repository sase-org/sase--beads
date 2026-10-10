# Bead: sase-1j6.10.1 — Restrict healer targets to skew-shaped failures and stop loud or phantom side effects

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.1` · **Size:** medium
**Created:** 2026-10-10 08:09:06 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

sweep-safety: make the scheduler job and `run -p` consider only doorbells, in-flight recovery rows, skew-suspect rows, and recent legacy skew-shaped rows; never claim, write, or notify for any other failure; stop write_recovery from recreating missing or wiped artifacts dirs; delete doorbells once owned; make the disabled and paused paths resurface each silenced failure exactly once; trip the storm breaker once; keep idle ticks cheap.

## Dependencies

- **Blocks:** [sase-1j6.10.5](sase-1j6.10.5.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.1/README.md) | [sase-1j6.10.1](sase-1j6.10.1.md) | 0 |
