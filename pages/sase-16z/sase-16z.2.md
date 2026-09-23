# Bead: sase-16z.2 — sase-core: floors, jitter, parking, hot cadence, and reservation reads in admission

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.2` · **Size:** medium
**Created:** 2026-09-23 11:06:11 EDT · **Closed:** 2026-09-23 12:35:25 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

core-admission-policy: extend due/admit evaluation (opt-in via `adaptive` and new optional request fields) with per-provider polling floors, deterministic ±10% jitter, CLI-fingerprint unparking, and hot cadence (hot hints, warn-level windows, passive-coverage suppression). Add a `mark_provider_usage_hot` store operation, a read-only live-reservation listing, and per-provider floor-aware freshness on reads, all with bindings and golden legacy-compat tests.

## Notes

[2026-09-23T16:34:48Z · sase-16z.2] PROPOSED FOLLOW-UP: fleet gateway route tests (fleet_attention_read_empty_request_touches_no_notification_store, fleet_enrollment_and_hello, fleet_launch_replays_delayed_launch) failed once under the full parallel check lane and passed on retry plus 221/221 in isolation; no provider_usage dependency, looks like a load flake with no flake bead yet

[2026-09-23T16:35:25Z · sase-16z.2] Implemented core-admission-policy in sase-core: adaptive due/admit fields, FNV jitter in [0.9,1.1] on cadence+backoff, floor/parked/cli_changed reasons, hot_until hints with cap+coalescing, live reservation listing, floor-aware reads, bindings, golden legacy tests. Verified: 129 provider_usage core tests, 10 provider_policy binding tests, 221 gateway lib tests pass; sase tool run check succeeded (a79575b7). No epic symbols.

## Dependencies

- **Depends on:** [sase-16z.1](sase-16z.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.5](sase-16z.5.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.2/README.md) | [sase-16z.2](sase-16z.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cfe1902`](https://github.com/sase-org/sase-core/commit/cfe1902a69919b2860c87bdae8b15b52c99d49ca) | feat!: adaptive admission policy for provider usage | [sase-16z.2](sase-16z.2.md) | 2026-09-23 12:37:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16z.2][1] | check epic symbols before close prep | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.2/README.md

<!-- sase:referenced-by:end -->
