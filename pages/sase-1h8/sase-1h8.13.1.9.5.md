# Bead: sase-1h8.13.1.9.5 — Claims, ready marking and dependencies as single view algorithms

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.5` · **Size:** medium
**Created:** 2026-10-08 21:24:21 EDT · **Closed:** 2026-10-09 00:30:00 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

unify-claims-deps: run launch/wait claims, release, epic preclaim, mark/unmark ready, and dependency and reference add/remove through the view-commit runner on both backings, and delete their replay copies; suites and goldens stay green.

## Notes

[2026-10-09T04:30:00Z · sase-1h8.13.1.9.5] unify-claims-deps done: claim_for_agent_launch/wait, release_agent_claim, preclaim_epic_work_plan (claims.rs), set_ready_to_work incl mark/unmark (store.rs), add/remove_dependencies and add/remove_bead_references (dependencies.rs) now run as single MutationView algorithms through runner::run_mutation on both backings; all try_cached_* fns, MutableStore replay copies, per-family stream/config loading and durable_store_error deleted; claims keep raw-ID lookups, deps/ready keep view shorthand resolution, blocker status stays on target point lookups. Verified: just fmt, just fast, bead::mutation 243 pass, bead::read_model 20 pass, parity/proof 35+2+6+16 pass, sase_core_py 297 pass, sase tool run check exit=0. epic-symbols clean. No new tests: dual-mode suites, replay_goldens, claims_deps warm suite and proof tests already exercise every unified entry point on both backings.

## Dependencies

- **Depends on:** [sase-1h8.13.1.9.3](sase-1h8.13.1.9.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.5/README.md) | [sase-1h8.13.1.9.5](sase-1h8.13.1.9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8e93d01`](https://github.com/sase-org/sase-core/commit/8e93d017e9e46e2813d901052d3c0aaa8b76a804) | feat(beads): unify claims, ready marking and dependencies on one view commit | [sase-1h8.13.1.9.5](sase-1h8.13.1.9.5.md) | 2026-10-09 00:32:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.9.5][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.5/README.md

<!-- sase:referenced-by:end -->
