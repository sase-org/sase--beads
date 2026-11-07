# Bead: sase-1rq.3.1.3 — Run the full macOS CI test set to green on the mac host

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.3` · **Size:** large
**Created:** 2026-11-07 08:10:12 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

## Description

mac-full-suite: on a tree that contains the mac-known-failures fixes, run every command CI's macOS job runs on the mac host, with a per-binary watchdog. Every test binary after gcal_auth (all gmail_* suites, gcal_*, gkeep_*, randomize, tasks_parity, tasks_real_vault_parity, doctests) has not run on macOS since about 2026-11-02. Fix every remaining failure or hang, and show that the macOS test step fits well inside its unchanged 45-minute job timeout.

## Dependencies

- **Depends on:** [sase-1rq.3.1.2](sase-1rq.3.1.2.md) ◐ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.3/README.md) | [sase-1rq.3.1.3](sase-1rq.3.1.3.md) | 0 |
