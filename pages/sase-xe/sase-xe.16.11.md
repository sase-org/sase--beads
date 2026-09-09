# Bead: sase-xe.16.11 — Finish remote dispatch setup correctness and live acceptance

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.11

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.land`
**Created:** 2026-09-09 04:38:25 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remote_dispatch_landing_remaining.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md

<!-- sase:links:end -->

## Description

Remote setup preserves discovery failures, activates enrollments through durable operations, uses Rust-owned shared policy, and has real fault and Athena-to-Apollo evidence sufficient to resume the interrupted sase-xe.16 landing.

## Notes

[2026-09-09T12:35:55Z · research.1p.final] DISCOVERED ISSUE: Independent live Apollo Fleet/Focus contract reproduction on 2026-09-09 08:28-08:35 EDT, SASE 27bbd2f4e4bcab9c364b175ad44c3fa24e13250d and reviewed core 7af26400fbca87eb70102c7082a1b029c65e310b. Authenticated hello and Serve work. ACE sends catalog limit 250 but the gateway caps 100; legal pages return 152 records (90 DONE) yet project_fleet_agents returns zero rows and no diagnostic because it ignores hosts[].payload.page.rows and hosts[].error. include_terminal is omitted; no continuation is consumed. Traversal-only projection yields 100 attempt-0 rows with missing provider/origin and a false count of 100 versus authoritative running=1. Raw worker hosts also fail the Rust count input schema. Additional lead finding: Focus sends logical_locators where FleetLogicalBatchRequestWire requires logical_keys; live equivalent requests fail with mismatched request_id versus resolving the known DONE record successfully. These block live phase sase-xe.16.11.5 and are absent from the current assigned repair scopes. Recommend explicit Fleet/Focus wire repair inside this epic before .5, with real ACE-request/worker-response regression coverage, terminal paging, authoritative counts, correct metadata/origin, and host-error visibility. Preserve current setup work and require known recent DONE plus active remote launch/follow/output/stop/restart evidence. No standalone task or dependency changes made. Consolidated evidence: research:202609/apollo_fleet_contract_repair/apollo_fleet_contract_repair.md; immutable snapshot file:explicit:42276af3c0f32fd66859f99d. Researcher A/B preserved unchanged alongside it.

[2026-09-09T12:51:37Z · sase-yt.land] DISCOVERED ISSUE from proposing bead sase-yt.2 note #1: On Athena on 2026-09-09, sase machine status apollo -j returns ok=false, state=error, message="machine alias is not configured", with empty endpoint/installation/provider because the loaded dispatch.machines map is empty. This is independent of sase-yt gateway supervision: both managed gateways are enabled/active, loopback-only, cross-tailnet healthy, and Apollo authenticated hello was separately proven. The linked chezmoi source home/dot_config/sase/sase_athena.yml has no dispatch entry. This is causally owned by this active remote-dispatch epic, especially phase sase-xe.16.11.5 canonical machine init plus authenticated status acceptance; ensure its live workflow durably creates/restores the apollo alias. /sase_new_task duplicate searches and recent-task sweep found no matching standalone task, so none was created.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.land/README.md) | [sase-xe.16.11](sase-xe.16.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1p.final][1] | Record the active epic ownership and current Fleet repair gap for the consolidated research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1p.final/README.md

<!-- sase:referenced-by:end -->
