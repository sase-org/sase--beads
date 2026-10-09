# Bead: sase-1h8.13.1.5 — Port claims, ready marking and dependencies onto the mutation view

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.5` · **Size:** medium
**Created:** 2026-10-08 14:46:06 EDT · **Closed:** 2026-10-08 19:06:50 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

## Description

port-claims-deps: move claims.rs (wait and launch claims, release, all-or-nothing epic preclaim), ready marking in store.rs, and dependencies.rs (dependency and reference add/remove, blocker status) onto the view with affected-row-only work, dual-mode tests and cached-path counters.

## Notes

[2026-10-08T23:06:50Z · sase-1h8.13.1.5] Ported claims (launch/wait/release/preclaim), ready marking, and dependencies/references onto MutationView with affected-row-only work. Each entry point tries the cached view first (single-row/stream loads, staged overlay, shared commit_staged_write) and falls back to replay on missing streams. Blocker status now comes from dependency-target point lookups via active_blockers_via_view, never a whole-store scan. New tests/claims_deps.rs adds 7 warm-path tests asserting zero full replays/snapshot loads, one admission sweep, and bounded hydration/stream reads plus cache-equals-replay. Verified: bead::mutation 200 pass, bead::read_model 20 pass, bead_read_model_parity 6 pass, bead_read_parity 16 pass, bead_event_parity 35 pass, sase_core_py 296 pass, and full sase tool run check green (exit 0). sase bead epic-symbols shows no leftovers.

## Dependencies

- **Depends on:** [sase-1h8.13.1.3](sase-1h8.13.1.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.7](sase-1h8.13.1.7.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.5/README.md) | [sase-1h8.13.1.5](sase-1h8.13.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d18537a`](https://github.com/sase-org/sase-core/commit/d18537a5cae17179505ff71593fe55f8673f8260) | feat(beads): port claims, ready marking and dependencies onto the mutation view | [sase-1h8.13.1.5](sase-1h8.13.1.5.md) | 2026-10-08 19:08:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.5][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1h8.13.1.7][2] | sibling evidence for proof baseline | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.7/README.md

<!-- sase:referenced-by:end -->
