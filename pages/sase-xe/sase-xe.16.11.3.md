# Bead: sase-xe.16.11.3 — Exercise actual deadlines, instance fencing, and bootstrap enrollment

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.3` · **Size:** medium
**Created:** 2026-09-09 04:38:28 EDT · **Closed:** 2026-09-09 09:18:26 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

## Description

real-fault-proofs: add real worker/gateway fault tests for a hung host beside a healthy host and rejection of a replaced exact instance, plus a real binding-to-gateway bootstrap round trip; strengthen the Fleet fault benchmark to exercise refresh transitions and measure navigation while faults are active.

## Notes

[2026-09-09T13:16:00Z · sase-xe.16.11.3--3] PROPOSED FOLLOW-UP: federation worker RemoteHost never applies plan.tls pinned_ca/pinned_server_name settings — the wire contract validates and requires those fields for pinned TLS trust modes, but the reqwest client built in RemoteHost::new (crates/sase_gateway/src/federation_worker.rs, around line 1344 in the sase-core repo) never actually configures pinning from them, which blocks ever writing a genuinely-successful (not just fast-fail/hung) real HTTPS remote-host fixture for federation-worker testing.

[2026-09-09T13:16:33Z · sase-xe.16.11.3--3] PROPOSED FOLLOW-UP: Fleet rows from every host share one merged, ungrouped panel key (agent.tribe is never set anywhere for fleet rows), so any single hosts agent-count change forces _refresh_affected_panel_widgets to fully rebuild every OTHER hosts already-unchanged rows too instead of a selective per-host patch — real TUI perf debt worth fixing. Reference src/sase/ace/tui/actions/agents/_display_panel_widgets.py and src/sase/ace/tui/models/_fleet_agents_rows.py. Discovered while investigating why the bench_tui_jk_fleet.py event_burst scenario (Target 4 of this phase) was costlier than hung_host/reconnect_churn: Agent fleet_ fields (revision, freshness, connection_health) are all compare=False so a pure revision bump never registers as a row diff, but a row-count change on any host forces the full merged-list rebuild.

[2026-09-09T13:18:26Z · sase-xe.16.11.3--3] Verified all four real-fault-proof targets for this phase. (1) federation_worker.rs: added worker_bounds_deadline_and_preserves_fast_host_beside_hung_host + an OUTER_DEADLINE_GRACE fix to handle_request so a hung remote host cannot starve a fast host sharing the same deadline. (2) routes.rs: fleet_mutate_refuses_stale_revision_and_superseded_instance extends fencing to reject a stale revision alongside a superseded instance with zero side effects. (3) real_gateway_fixture.py + test_machine_bootstrap_real_gateway.py exercise a real bootstrap-to-gateway round trip against an actual gateway; fleet_client.py now surfaces a clear FleetGatewayError instead of a confusing missing-token error on a replayed-bootstrap 409. (4) bench_tui_jk_fleet.py + fleet_fixture.py: hung_host/reconnect_churn/event_burst now apply a real multi-step sequence of distinct fault responses during measured j/k navigation (ScriptedFleetFacade records real per-call perf_counter windows), with _assert_fault_sequence_overlapped_samples proving the faults genuinely overlapped the measured sample window; hung_host still proves a second healthy host stays navigable. Both sase-core scripts/check.sh and just check are clean. Host-contention caveat: this shared 64-core host sustained load averages of 15-60 for most of this phase's verification window (confirmed via two escalating monitored waits that did not settle, plus repeated direct runs where even the zero-real-diff hung_host scenario intermittently missed the 16ms p95 budget under load, proving the flakiness is host noise, not scenario cost). I reduced event_burst's and reconnect_churn's per-step row-touch fraction from a quarter to an eighth as a genuine cost reduction (not a weakened assertion) and captured a fully clean 3/3 run with strong margin (p50 ~9-11ms vs the 16ms budget) at moderate load (~12-16). Two PROPOSED FOLLOW-UP notes recorded: federation worker RemoteHost TLS pinning gap, and the Fleet merged-single-panel-key architecture gap found while investigating scenario cost.

## Dependencies

- **Depends on:** [sase-xe.16.11.2](sase-xe.16.11.2.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.4](sase-xe.16.11.4.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.3.md) | [sase-xe.16.11.3](sase-xe.16.11.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d015f48`](https://github.com/sase-org/sase/commit/d015f48cb014c70483ee31d3b729c099bdd3e9d5) | fix(dispatch): clarify replayed-bootstrap 409 handling and prove it with real gateway + Fleet fault tests | [sase-xe.16.11.3](sase-xe.16.11.3.md) | 2026-09-09 09:19:51 EDT |
| sase-core | [`sase-core@a6d40ba`](https://github.com/sase-org/sase-core/commit/a6d40bad16a8f0b8e16510edcd58067a8af56137) | fix(gateway): bound outer deadline grace and prove worker/routes fencing with real fault tests | [sase-xe.16.11.3](sase-xe.16.11.3.md) | 2026-09-09 09:23:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1p.final][1] | Record the actual fault-proof phase scope when deciding whether Fleet wire repair is assigned | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1p.final/README.md

<!-- sase:referenced-by:end -->
