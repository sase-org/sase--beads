# Bead: sase-xe.16.11.7.1 — Rust fleet read contract - normalization, counts, freshness, continuation

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hv.md) · **Assignee:** `sase-xe.16.11.7.1` · **Size:** medium
**Created:** 2026-09-09 15:49:26 EDT · **Closed:** 2026-09-09 16:44:16 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

## Description

fleet-wire: normalize real federation envelopes, own counts and freshness in sase_core, add per-host continuation types, and export the bindings.

## Notes

[2026-09-09T20:43:35Z · sase-xe.16.11.7.1] Rust/PyO3 fleet-wire surface exported for downstream: normalize_fleet_federation_response(FleetFederationNormalizeRequestWire { schema_version, response }) -> FleetNormalizedReadResponseWire { schema_version, operation, configured_host_count, partial, summaries, diagnostics, hosts, count_hosts }; count_focus_and_fleet_from_federation(FocusFleetFederationCountsRequestWire { schema_version, local_summaries, followed_response, fleet_response }) -> FocusFleetCountsWire; validate_fleet_catalog_cursor(cursor) -> cursor string; validate_fleet_logical_agent_counts(counts, label) -> counts clone. FleetNormalizedHostWire fields: schema_version, alias, origin, status, cached, age_seconds, partial, freshness, observed_at_unix, summaries, authoritative_counts, count_revision, catalog, unresolved_logical_keys, diagnostics, count_input. FleetCatalogContinuationWire fields: schema_version, snapshot_cursor, limit, total_matching_rows, next_cursor, has_more, state ready|finished|resync_required. FleetHostCountInputWire adds authoritative_counts and partial. PyO3 exports: fleet_validate_catalog_query, fleet_validate_catalog_cursor, fleet_validate_snapshot_freshness, fleet_normalize_federation_response, fleet_count_focus_and_fleet_from_federation.

[2026-09-09T20:44:16Z · sase-xe.16.11.7.1] Verified cargo test -p sase_core federation_, cargo test -p sase_core focus_and_fleet_counts_stay_separate_and_propagate_unknown_hosts, cargo test -p sase_core fleet_contract::tests::, cargo test -p sase_core_py fleet_, cargo test -p sase_core_py gateway_and_bootstrap_bindings_are_registered, cargo check -p sase_core_py, and git diff --check.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.3](sase-xe.16.11.7.3.md) ◐ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.5](sase-xe.16.11.7.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.1/README.md) | [sase-xe.16.11.7.1](sase-xe.16.11.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6b29558`](https://github.com/sase-org/sase-core/commit/6b29558e8ac031df97133fd2a4991dd67f339ee2) | feat(fleet): normalize federation read envelopes | [sase-xe.16.11.7.1](sase-xe.16.11.7.1.md) | 2026-09-09 16:45:52 EDT |
