# Bead: sase-1j1.5 — sase fleet client stops amplifying slow hosts

[Bead Pages](../README.md) / [sase-1j1](README.md) / sase-1j1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yx.md) · **Assignee:** `sase-1j1.5` · **Size:** medium
**Created:** 2026-10-09 09:31:13 EDT · **Closed:** 2026-10-09 11:23:02 EDT
**Plan:** [202610/apollo\_gateway\_snapshot\_stampede.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_gateway_snapshot_stampede.md)

## Description

fleet-client-hardening: in sase Python, give the IPC socket a grace period beyond the worker deadline, classify socket timeouts separately, and stop respawning and resending on a slow-but-alive worker. Make the TUI fleet refresh single-flight with one pending rerun. Add schema_version to the fallback diagnostics, and degrade normalization failures to a visible fleet error.

## Notes

[2026-10-09T15:22:53Z · sase-1j1.5--1] PROPOSED FOLLOW-UP: tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree timed out on PTY marker under full-lane load (load 40-80) in tool run 0deb942ff544651a160d5c2dd8abdfae, passes 2/2 in isolation on both base and phase tree; already tracked by flake task sase-13a

[2026-10-09T15:23:02Z · sase-1j1.5--1] fleet-client-hardening verified: 22 phase tests pass (test_dispatch_federation 17, fleet coalescing 5), ruff+mypy clean, full check 54226 passed with 1 unrelated load-flake zsh sbd alias timeout already tracked by sase-13a and passing 2/2 isolated on base and phase tree; no epic-symbols remain

## Dependencies

- **Blocks:** [sase-1j1.6](sase-1j1.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j1.5.md) | [sase-1j1.5](sase-1j1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d7c4958`](https://github.com/sase-org/sase/commit/d7c495855154f1e3ff62beec3a16e56cd8b9de86) | fix(fleet): stop sase fleet client amplifying slow hosts | [sase-1j1.5](sase-1j1.5.md) | 2026-10-09 11:27:17 EDT |
