# Bead: sase-k0.3 — Settle bead gates from sase bead close

[Bead Pages](../README.md) / [sase-k0](README.md) / sase-k0.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yk/README.md) · **Assignee:** `sase-k0.3` · **Size:** medium
**Created:** 2026-08-12 10:58:54 EDT
**Plan:** [202608/task\_gate\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_gate_convergence.md)

## Description

close_settle: have the close command cancel each closed task bead's pending gate right after the store mutation commits, so the existing notifications inotify watch refreshes ACE at once, and keep the added cost off closes that cannot have gates.

## Dependencies

- **Depends on:** [sase-k0.1](sase-k0.1.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.3/README.md) | [sase-k0.3](sase-k0.3.md) | 0 |
