# Bead: sase-11y.10.1.3.1.5 — Delete the AXE restart machinery the alias orphaned

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.5` · **Size:** medium
**Created:** 2026-09-20 21:18:01 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

dead-supervisors: delete `_process_restart.py`, `_restart_events.py`, `restart_render.py`, and `status_render.py` once the alias removes their last callers, and prune the `sase.axe.process` / `sase.axe` re-export surface that kept a second supervisor reachable.

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.5/README.md) | [sase-11y.10.1.3.1.5](sase-11y.10.1.3.1.5.md) | 0 |
