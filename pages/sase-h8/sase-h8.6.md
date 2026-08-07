# Bead: sase-h8.6 — Fix the ACE fixture-state and cross-test-leakage family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.6` · **Size:** medium
**Created:** 2026-08-07 18:05:44 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

fixture: fix the triaged ACE nodes whose injected fixture state is overwritten by a queued repaint or leaks across tests, by making state injection settle-verified and the affected panes isolated per test.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.6/README.md) | [sase-h8.6](sase-h8.6.md) | 0 |
