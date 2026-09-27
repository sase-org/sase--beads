# Bead: sase-1bc.3 — sase-core scan wire and fleet contract carry agent\_tab

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.3` · **Size:** medium
**Created:** 2026-09-27 10:57:03 EDT · **Closed:** 2026-09-27 12:25:00 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

core-tab-wires: add agent_tab/agent_tab_source to the scan wire (schema 11) and agent_tab to the fleet owner and summary wires (contract 7) with root inheritance in fleet_catalog, gateway owner facts, stable revisions, validation, and a breaking-change marker.

## Notes

[2026-09-27T16:25:00Z · sase-1bc.3] core-tab-wires done in sase-core working tree (uncommitted for land agent). Scan wire 10->11 with AgentMetaWire.agent_tab/agent_tab_source, validated via canonicalize (main->absent, invalid dropped). Fleet contract 6->7 with agent_tab on OwnerResolutionFactsWire and ResolvedAgentSummaryWire (default+skip-if-none), tribe-parallel projection/validation, root inheritance in fleet_catalog, stable_revision hash, gateway fill plus contract docs and regenerated fleet_api_v1 snapshot. Tests: v6 decode/V7 round-trip/newer-version rejection, inheritance, revision change, scanner canonicalization. sase tool run check green (f5b432ad). One transient hit of known flake sase-17n (private_argv test, unrelated tool_run area) passed alone 8/8. Suggested commit: feat!: with BREAKING CHANGE footer 'upgrade controllers first, or the fleet in lockstep'. No index schema bump needed (index stores full record_json and round-trips). sase Python mirror left for sase-1bc.4 per plan.

## Dependencies

- **Depends on:** [sase-1bc.2](sase-1bc.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.4](sase-1bc.4.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.3/README.md) | [sase-1bc.3](sase-1bc.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0e8981a`](https://github.com/sase-org/sase-core/commit/0e8981a1f131d2dd040c4887ae949edf19fbeef6) | feat!: carry agent\_tab on scan wire (schema 11) and fleet contract (v7) | [sase-1bc.3](sase-1bc.3.md) | 2026-09-27 12:32:28 EDT |
