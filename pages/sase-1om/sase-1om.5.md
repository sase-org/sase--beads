# Bead: sase-1om.5 — Retire the Python holder predicate behind sase agent list

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.5` · **Size:** small
**Created:** 2026-10-26 20:19:45 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

list-holder-parity: source `holds_runner_slot`, `runner_slot_holders`, and `runner_slots_in_use` in `sase agent list -j` from Rust accounting, delete `runner_slot_holder_dirs` and the `status == "RUNNING"` fallback, and add per-entry capacity fields.

## Dependencies

- **Depends on:** [sase-1om.3](sase-1om.3.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.5/README.md) | [sase-1om.5](sase-1om.5.md) | 0 |
