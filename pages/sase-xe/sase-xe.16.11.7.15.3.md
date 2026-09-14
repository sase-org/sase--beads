# Bead: sase-xe.16.11.7.15.3 — Core wire carries the missing presentation facts

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.3` · **Size:** large
**Created:** 2026-09-13 18:38:04 EDT · **Closed:** 2026-09-13 20:05:41 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

wire-parity-fields: renderer-driven audit of Agent fields versus wire sources, then extend ResolvedAgentSummaryWire and the owner projection with start/stop timestamps, workspace number, clan/tribe identity, and a human project label; bump contract schema, bindings, and fixtures with full core checks.

## Notes

[2026-09-14T00:03:28Z · sase-xe.16.11.7.15.3--1] Renderer audit: start_time -> ResolvedAgentSummaryWire.started_at_unix; stop_time -> stopped_at_unix; workspace_num -> workspace_num; project_display_name -> labels.project_label; agent_clan -> agent_clan; agent_clan_generation -> agent_clan_generation; clan_tribe -> clan_tribe; tribe -> tribe. project_name remains the portable project id for locators/query/grouping. Existing remote-ready fields remain model, provider, status, status_bucket, intent, queue weights, row_kind, family_role, parent_timestamp, current_instance, container_projected_concrete_agent, dismissable, needs_attention, occupied_runner_slot, capabilities, and content. Non-goals remain excluded: local paths, PIDs, raw monitor/gate commands, artifact dirs, output paths, and response paths.

[2026-09-14T00:03:32Z · sase-xe.16.11.7.15.3--1] Published surface: fleet contract schema v2 is emitted with v1 read compatibility; OwnerResolutionFactsWire accepts started_at_unix, stopped_at_unix, workspace_num, project_label, agent_clan, agent_clan_generation, clan_tribe, and tribe; ResolvedAgentSummaryWire publishes started_at_unix, stopped_at_unix, workspace_num, agent_clan, agent_clan_generation, clan_tribe, tribe, and labels.project_label. PyO3 surfaces cover fleet_project_resolved_agent_summary, fleet_project_resolved_agent_detail, fleet_validate_resolved_agent_summary, and the gateway /api/fleet/v1 hello, summary, catalog, batch, and detail summary/detail payloads. Follow-ups: F1 published-core-adoption waits for release-plz and ratchets SASE pin/floor without consuming a dev build; F2 remote-render-integration maps the new fields to Agent rows and handles project label fallback; F3 parity-proof asserts local vs remote rendered equality except host chip; F4 live-acceptance verifies Athena viewing Apollo with family/clan grouped remote nodes.

[2026-09-14T00:04:41Z · sase-xe.16.11.7.15.3--1] Published surface: fleet contract schema v2 is emitted with v1 read compatibility; OwnerResolutionFactsWire accepts started_at_unix, stopped_at_unix, workspace_num, project_label, agent_clan, agent_clan_generation, clan_tribe, and tribe; ResolvedAgentSummaryWire publishes started_at_unix, stopped_at_unix, workspace_num, agent_clan, agent_clan_generation, clan_tribe, tribe, and labels.project_label. PyO3 surfaces cover fleet_project_resolved_agent_summary, fleet_project_resolved_agent_detail, fleet_validate_resolved_agent_summary, and the gateway /api/fleet/v1 hello, summary, catalog, batch, and detail summary/detail payloads. Follow-ups: F1 published-core-adoption waits for release-plz and ratchets SASE pin/floor without consuming a dev build; F2 remote-render-integration maps the new fields to Agent rows and handles project label fallback; F3 parity-proof asserts local vs remote rendered equality except host chip; F4 live-acceptance verifies Athena viewing Apollo with family/clan grouped remote nodes.

[2026-09-14T00:05:41Z · sase-xe.16.11.7.15.3--1] Implemented fleet wire parity fields in core/gateway: fleet contract schema v2 remains read-compatible with v1, PyO3 bindings round-trip the new owner/rendering facts, the fleet API contract snapshot documents the published fields, and added/updated tests cover projection, PyO3, gateway contract, and route fixtures. Verification: core just check passed after targeted PyO3, contract snapshot, and gateway route tests.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.15.3.md) | [sase-xe.16.11.7.15.3](sase-xe.16.11.7.15.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d0ec62c`](https://github.com/sase-org/sase-core/commit/d0ec62c329e228a2b04f30bc4d087969c895ddf8) | feat(fleet): publish remote renderer parity fields | [sase-xe.16.11.7.15.3](sase-xe.16.11.7.15.3.md) | 2026-09-13 20:11:57 EDT |
