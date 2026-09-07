# Bead: sase-xe.13 — Remote lifecycle management parity

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.13` · **Size:** large
**Created:** 2026-09-06 14:06:48 EDT · **Closed:** 2026-09-07 09:25:13 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

remote-actions: execute kill/stop, retry, and fork-on-target for followed remote agents through the mutation journal with exact instance identity, stream bounded output/diff/chat content through opaque handles, and partition bulk actions per origin with honest per-target results.

## Notes

[2026-09-07T13:24:42Z · sase-xe.13] PROPOSED FOLLOW-UP: ratchet the pinned sase-core revision after the mutation-contract core commit lands so CI's pinned-binding gate sees fleet_mutation_* bindings. sase-core-revision.txt is still 2fba6e44810370c27beab563597667e1d1d35351; this phase did not bump it. just check's core-floor-probe reported blocked_unpublished for fleet_evaluate_mutation_precondition, fleet_mutation_payload_fingerprint, fleet_partition_bulk_targets, and fleet_validate_mutation_request.

[2026-09-07T13:25:13Z · sase-xe.13] Remote lifecycle parity is implemented: journaled fleet mutate (stop/retry/fork-on-target) through sase-core, gateway POST /api/fleet/v1/mutate, federation Mutate IPC, Python facade/client, sase machine agent {fork,retry,stop}, and ACE origin-routed kill/fork/retry/content with optimistic UI and viewer purity. Verified sase-core ./scripts/check.sh all (fmt/clippy/workspace tests, including fleet contract snapshot) and sase just install + just sync-completion-spec + just check (escalated full suite). sase bead epic-symbols sase-xe.13 reported no remaining --epic-symbol entries. Did not ratchet sase-core-revision.txt; recorded the pinned-core follow-up on this phase bead.

## Dependencies

- **Depends on:** [sase-xe.11](sase-xe.11.md) ✓ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.12](sase-xe.12.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.14](sase-xe.14.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.13.md) | [sase-xe.13](sase-xe.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a3a12a`](https://github.com/sase-org/sase/commit/1a3a12a7eff807fa93da4d788242a3adbfba5b6d) | feat(dispatch): add remote fleet stop, retry, fork, and bounded content | [sase-xe.13](sase-xe.13.md) | 2026-09-07 09:27:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-xe.13][1] | Need assigned phase scope, status, and notes before implementing remote action parity | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.13.md

<!-- sase:referenced-by:end -->
