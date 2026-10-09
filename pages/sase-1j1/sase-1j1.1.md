# Bead: sase-1j1.1 — Single-flight, back-off, and bounded index work in FleetReadService

[Bead Pages](../README.md) / [sase-1j1](README.md) / sase-1j1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yx.md) · **Assignee:** `sase-1j1.1` · **Size:** medium
**Created:** 2026-10-09 09:31:11 EDT · **Closed:** 2026-10-09 10:30:03 EDT
**Plan:** [202610/apollo\_gateway\_snapshot\_stampede.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_gateway_snapshot_stampede.md)

## Description

gateway-single-flight: in sase-core, rewrite the FleetReadService snapshot refresh. Each scope gets one detached in-flight build that always fills the cache when it finishes. Callers wait up to the timeout. Failures back off exponentially. A shared semaphore bounds index work, the overlay pass is coalesced and best-effort, and the gateway runtime caps blocking threads. Includes a slow-build stampede regression test.

## Notes

[2026-10-09T14:29:43Z · sase-1j1.1] PROPOSED FOLLOW-UP: full `sase tool run check` in sase-core shows two pre-existing load flakes in untouched sase_core files (both pass alone on the clean base tree): tool_run::store::tests::private_argv_is_not_serialized_on_queries (already tracked by flake bead sase-17n) and provider_priority::tests::concurrent_priority_changes_and_auto_disables_are_serialized (LockTimeout under the full parallel lane)

[2026-10-09T14:30:03Z · sase-1j1.1] gateway-single-flight done in sase-core: per-scope single-flight refresh with detached builds that always fill cache, 4s caller waits, 15s doubling back-off capped at 120s, 2-permit index semaphore, coalesced+memoized best-effort overlay, 32-thread runtime cap. Verified: just test -p sase_gateway 237 passed incl 6 new refresh tests (stampede, late-fill, back-off+reset, cold-cache, force, overlay); fmt/features/clippy clean via sase tool run check; 2 sase_core load flakes reproduce on clean base (noted as follow-up). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1j1.4](sase-1j1.4.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j1.6](sase-1j1.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j1.1/README.md) | [sase-1j1.1](sase-1j1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c02edc5`](https://github.com/sase-org/sase-core/commit/c02edc5bbfa8875733c9f689eedee9fc240eda74) | feat(fleet-reads): bound refresh stampedes with single in-flight build and backoff | [sase-1j1.1](sase-1j1.1.md) | 2026-10-09 10:31:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j1.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j1.1/README.md

<!-- sase:referenced-by:end -->
