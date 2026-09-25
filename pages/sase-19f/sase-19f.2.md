# Bead: sase-19f.2 — Rust admission resolution, scan records, and fleet contract

[Bead Pages](../README.md) / [sase-19f](README.md) / sase-19f.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1o.md) · **Assignee:** `sase-19f.2` · **Size:** medium
**Created:** 2026-09-25 12:24:37 EDT · **Closed:** 2026-09-25 13:34:01 EDT
**Plan:** [202609/queue\_capacity\_multiplier.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_multiplier.md)

## Description

core-admission: in sase-core, resolve a persisted multiplier against the request's effective_limit when computing the admission limit, add the field to runner-capacity records and waiters, agent-scan meta and waiting wires (with an index schema bump), and the fleet summary contract, and extend the normalize binding.

## Notes

[2026-09-25T17:33:07Z · sase-19f.2] PROPOSED FOLLOW-UP: `sase tool run check` is red on pre-existing Clippy lints in agent_runtime.rs, agent_scan/index/maintenance.rs, fleet_owner_facts.rs, provider_usage/mod.rs, and tool_run/store/triage.rs; this phase does not modify those files.

[2026-09-25T17:34:01Z · sase-19f.2] Implemented multiplier admission normalization, runner/scan/fleet wires, index refresh, Python binding, and fleet contract. Verified just fast; focused runner, scanner, fleet, and binding tests; and regenerated/passed the gateway contract test. Guarded full check is blocked by recorded unrelated clean-base Clippy findings.

## Dependencies

- **Depends on:** [sase-19f.1](sase-19f.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19f.3](sase-19f.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19f.2/README.md) | [sase-19f.2](sase-19f.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@96e42d9`](https://github.com/sase-org/sase-core/commit/96e42d944689412c45a39035764f3422acf261bb) | feat(queue): resolve capacity multipliers at admission | [sase-19f.2](sase-19f.2.md) | 2026-09-25 13:35:22 EDT |
