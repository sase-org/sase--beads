# Bead: sase-1h8.13.1.4 — Port open, close and remove onto the mutation view

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.4` · **Size:** medium
**Created:** 2026-10-08 14:46:05 EDT · **Closed:** 2026-10-08 19:04:40 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

## Description

port-lifecycle: move close_remove.rs (open, close, close with note, descendant guards, delegated-parent completion, ancestor reopening, removal cascades and survivor dependency cleanup) onto the view with affected-row-only work, dual-mode tests and cached-path counters.

## Notes

[2026-10-08T23:04:12Z · sase-1h8.13.1.4] PROPOSED FOLLOW-UP: sase tool run check shows provider_priority::tests::concurrent_priority_changes_and_auto_disables_are_serialized failing with LockTimeout under the full parallel lane while passing alone (22/22 provider_priority pass isolated); already tracked by flake bead sase-yn

[2026-10-08T23:04:40Z · sase-1h8.13.1.4] Ported open/close/remove onto MutationView: try_cached_open/close/remove mirror replay outcomes, orderings and error text with affected-row-only loads, reverse-dependent survivor cleanup and delegated-parent completion via children lookup; 12 new lifecycle_warm tests prove zero full replays/snapshot loads, bounded hydration and cache-equals-replay plus cached/replay convergence. Verified: 205 mutation + 20 read_model + 51 parity + 296 py pass, fmt/clippy clean, full check 4689 pass except known provider_priority load flake (passes alone, tracked by sase-yn, filed as follow-up). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h8.13.1.3](sase-1h8.13.1.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.7](sase-1h8.13.1.7.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.4/README.md) | [sase-1h8.13.1.4](sase-1h8.13.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@276b14a`](https://github.com/sase-org/sase-core/commit/276b14a40f300c07e350a604682ba00200327e9b) | feat(beads): port open, close and remove onto the mutation view | [sase-1h8.13.1.4](sase-1h8.13.1.4.md) | 2026-10-08 19:05:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.4/README.md

<!-- sase:referenced-by:end -->
