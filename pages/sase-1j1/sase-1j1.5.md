# Bead: sase-1j1.5 — sase fleet client stops amplifying slow hosts

[Bead Pages](../README.md) / [sase-1j1](README.md) / sase-1j1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yx.md) · **Assignee:** `sase-1j1.5` · **Size:** medium
**Created:** 2026-10-09 09:31:13 EDT
**Plan:** [202610/apollo\_gateway\_snapshot\_stampede.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_gateway_snapshot_stampede.md)

## Description

fleet-client-hardening: in sase Python, give the IPC socket a grace period beyond the worker deadline, classify socket timeouts separately, and stop respawning and resending on a slow-but-alive worker. Make the TUI fleet refresh single-flight with one pending rerun. Add schema_version to the fallback diagnostics, and degrade normalization failures to a visible fleet error.

## Dependencies

- **Blocks:** [sase-1j1.6](sase-1j1.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j1.5.md) | [sase-1j1.5](sase-1j1.5.md) | 0 |
