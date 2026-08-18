# Bead: sase-q0.5.2 — Refuse gh workflow steps that would prepare an occupied checkout

[Bead Pages](../README.md) / [sase-q0.5](sase-q0.5.md) / sase-q0.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-q0.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-q0.land.md) · **Assignee:** `sase-q0.5.2` · **Size:** medium
**Created:** 2026-08-18 17:40:17 EDT
**Plan:** [202608/gh\_plugin\_workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/gh_plugin_workspace_exclusivity.md)

## Description

gh_guard: write the per-checkout occupant record when gh__setup takes a workspace, clear it on release, and require the occupancy decision before gh__prepare stashes, gh__checkout checks out, or the GitHub submit path checks out, so a conflicting occupant fails the run instead of losing another agent's work.

## Dependencies

- **Depends on:** [sase-q0.5.1](sase-q0.5.1.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.5.2/README.md) | [sase-q0.5.2](sase-q0.5.2.md) | 0 |
