# Bead: sase-zn.6 — Extend scratch hygiene to agent-created build directories and disk pressure

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.6` · **Size:** medium
**Created:** 2026-09-11 12:20:22 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

tmp-hygiene: give agent-created cargo/build scratch a managed home the reaper can actually see, and add size-aware pressure reaping so a multi-gigabyte directory is not held for a purely time-based horizon.

## Dependencies

- **Depends on:** [sase-zn.1](sase-zn.1.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.8](sase-zn.8.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.6/README.md) | [sase-zn.6](sase-zn.6.md) | 0 |
