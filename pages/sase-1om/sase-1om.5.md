# Bead: sase-1om.5 — Retire the Python holder predicate behind sase agent list

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.5` · **Size:** small
**Created:** 2026-10-26 20:19:45 EDT · **Closed:** 2026-10-27 00:48:17 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

list-holder-parity: source `holds_runner_slot`, `runner_slot_holders`, and `runner_slots_in_use` in `sase agent list -j` from Rust accounting, delete `runner_slot_holder_dirs` and the `status == "RUNNING"` fallback, and add per-entry capacity fields.

## Notes

[2026-10-27T04:48:00Z · sase-1om.5] PROPOSED FOLLOW-UP: Rust agent_runtime.rs still has unweighted running_agent_slot_count / is_runner_slot_occupying_record with no non-test callers — Python listing visibility still uses the occupying predicate; retire or fold the Rust copies into snapshot accounting.

[2026-10-27T04:48:17Z · sase-1om.5] sase agent list -j now sources holds_runner_slot from Rust accounting (state==holding), runner_slot_holders from claims, and runner_slots_in_use from occupied_lanes; deleted runner_slot_holder_dirs and the status==RUNNING fallback; added capacity_state/charged/reason. Screenshot-shape parity: TESTING and WAITING CUTOVER holders match the report's six holding entries (5.0 occupied / 6 lanes). sase tool run check passed (dbb58c4277a4723dc0bad153b0cac47d).

## Dependencies

- **Depends on:** [sase-1om.3](sase-1om.3.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.5/README.md) | [sase-1om.5](sase-1om.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e2b04a8`](https://github.com/sase-org/sase/commit/e2b04a88e2a3653e2ce02c08ff30387cb4e083a5) | feat(agents): source list occupancy from Rust accounting | [sase-1om.5](sase-1om.5.md) | 2026-10-27 00:49:41 EDT |
