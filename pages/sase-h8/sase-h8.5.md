# Bead: sase-h8.5 — Fix the real-wall-clock-threshold family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.5` · **Size:** medium
**Created:** 2026-08-07 18:05:35 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

clock: remove the dependence on real elapsed wall-clock time from the stall watchdog tests and the other triaged deadline-shaped nodes, by driving them from an injectable time source or a load-normalized budget instead of loosening assertions again.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.5/README.md) | [sase-h8.5](sase-h8.5.md) | 0 |
