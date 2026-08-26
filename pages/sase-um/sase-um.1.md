# Bead: sase-um.1 — Fast per-SHA master gate

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.1` · **Size:** large
**Created:** 2026-08-26 19:12:24 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

gate: add master-gate.yml — a per-SHA, never-cancelled push lane that runs the whole fast suite in balanced shards plus the lint gate, gets the Rust core from a SHA-keyed wheel cache instead of a 9-minute source build, and adds its README badge.

## Dependencies

- **Blocks:** [sase-um.3](sase-um.3.md) ◐ · ⧖ 2026-08-26
- **Blocks:** [sase-um.5](sase-um.5.md) ◐ · ⧖ 2026-08-26
- **Blocks:** [sase-um.6](sase-um.6.md) ◐ · ⧖ 2026-08-26
- **Blocks:** [sase-um.7](sase-um.7.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.1.md) | [sase-um.1](sase-um.1.md) | 0 |
