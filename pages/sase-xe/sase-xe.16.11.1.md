# Bead: sase-xe.16.11.1 — Put discovery and enrollment reconciliation policy in Rust

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.1` · **Size:** medium
**Created:** 2026-09-09 04:38:26 EDT · **Closed:** 2026-09-09 05:03:42 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

## Description

core-setup-policy: port the newly added pure Tailnet parsing, endpoint and health classification, and enrollment reconciliation decisions into sase-core with versioned wire bindings and regression coverage; distinguish an explicitly unrelated healthy service from an older SASE gateway without a fleet field.

## Notes

[2026-09-09T09:03:02Z · sase-xe.16.11.1] Committed machine-setup surface for the adapter phase. Schema version is 1 (machine_setup_wire_schema_version).

Exported sase_core_rs bindings (dict-in/dict-out):
- machine_setup_wire_schema_version() -> int
- classify_tailnet_health(request: dict) -> dict
- classify_tailnet_discovery(request: dict) -> dict
- reconcile_machine_enrollments(request: dict) -> dict

Unsupported schema_version or a non-dict envelope raises ValueError. Status/peer malformations stay in-band as diagnostics (tailnet_status_malformed, tailnet_status_peer_invalid, tailnet_peer_not_mapping).

classify_tailnet_health request: {schema_version, alias, payload?, error_code?, error_reason?}. Result: {schema_version, compatibility: compatible|unknown|incompatible, reason, diagnostic?: {code, severity, alias, message}}. Protocol compatibility is derived from sase_core FLEET_PROTOCOL_VERSION (currently 1). Malformed version types (string/bool/float/mixed/non-array) are tailnet_probe_fleet_malformed. status=ok with no fleet and service missing/empty/sase_gateway is unknown (legacy SASE, tailnet_probe_fleet_unknown). status=ok with an explicit non-SASE service (e.g. unrelated) is incompatible (tailnet_probe_unrelated_service).

classify_tailnet_discovery request: {schema_version, status, endpoint_overrides?, health_observations?: [{endpoint, payload?, error_code?, error_reason?}]}. Result: {schema_version, peers: [{peer_key, alias, endpoint, endpoint_source, online, os_hint}], candidates: [{provider_ref, endpoint, display_name, machine_selector, installation_pin, detail}], diagnostics}. Covers map-shaped Peer parsing, extra/missing fields, self exclusion, trailing-dot DNS, HTTPS overrides, offline/OS advisories. Candidates always use provider_ref=builtin@tailnet and never infer machine_selector or installation_pin. Missing health observation yields compatibility=unknown, reason="health not observed".

reconcile_machine_enrollments request: {schema_version, candidates, enrolled: [{alias, provider_ref, endpoint, pinned_installation_id}]}. Result: {schema_version, items: [{candidate, status: new|enrolled|repair, alias, reason}]}. Pin match skips as enrolled; endpoint match with a different discovery pin routes to repair (`sase machine repair {alias}`); untrusted discovery hints do not overwrite enrolled pins.

Python still owns subprocess/HTTP I/O. Do not ratchet sase-core-revision or replace Python helpers until this surface is published (setup-integration).

[2026-09-09T09:03:42Z · sase-xe.16.11.1] Ported Tailnet peer/endpoint parsing, health classification (legacy SASE vs unrelated healthy service), and enrollment reconciliation into sase_core machine_setup with schema v1 dict bindings classify_tailnet_health/classify_tailnet_discovery/reconcile_machine_enrollments. Verified 16 Rust policy tests, PyO3 envelope tests, and scripts/check.sh fmt+clippy+workspace tests including PyO3.

## Dependencies

- **Blocks:** [sase-xe.16.11.2](sase-xe.16.11.2.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.1/README.md) | [sase-xe.16.11.1](sase-xe.16.11.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0318b31`](https://github.com/sase-org/sase-core/commit/0318b317e8bd96482f2dca4ea4819527ab907055) | feat(core): add Tailnet discovery and enrollment reconciliation policy | [sase-xe.16.11.1](sase-xe.16.11.1.md) | 2026-09-09 05:05:05 EDT |
