# Bead: sase-19f.1 — Rust multiplier syntax, formatting, launch wires, and editor metadata

[Bead Pages](../README.md) / [sase-19f](README.md) / sase-19f.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1o.md) · **Assignee:** `sase-19f.1` · **Size:** medium
**Created:** 2026-09-25 12:24:35 EDT · **Closed:** 2026-09-25 13:02:27 EDT
**Plan:** [202609/queue\_capacity\_multiplier.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_multiplier.md)

## Description

core-parse: in sase-core, parse and validate `<M>x` wherever `%queue` accepts capacity, carry it as `queue_capacity_multiplier` through QueueFieldsWire and the typed agent/proc launch wires, format it canonically, add helper bindings, and update the completion metadata.

## Notes

[2026-09-25T17:02:08Z · sase-19f.1] PROPOSED FOLLOW-UP: sase-core just check clippy -D warnings fails on clean HEAD c31b8cf (rustc 1.95) with clippy::nonminimal_bool in agent_runtime.rs:239, agent_scan/index/maintenance.rs:484, fleet_owner_facts.rs:443, tool_run/store/triage.rs:945 and clippy::manual_range_contains in provider_usage/mod.rs:480 and :506 — reproduced identically on the base tree; no existing task bead

[2026-09-25T17:02:27Z · sase-19f.1] Parsed and validated <M>x in sase-core queue_directive, carried queue_capacity_multiplier through QueueFieldsWire and agent/proc launch wires, formatted canonically, added parse/format/resolve helpers and bindings, and updated flag-on completion metadata. Workspace tests passed (3471 sase_core + LSP/py bindings). sase tool run check still fails clippy on clean HEAD c31b8cf (nonminimal_bool and manual_range_contains in untouched files); recorded as PROPOSED FOLLOW-UP. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-19f.2](sase-19f.2.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19f.1/README.md) | [sase-19f.1](sase-19f.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f55c63b`](https://github.com/sase-org/sase-core/commit/f55c63bc90fe5811bc381103b038a137f8a767dd) | feat(queue): parse and format %queue \<M\>x capacity multipliers | [sase-19f.1](sase-19f.1.md) | 2026-09-25 13:05:04 EDT |
