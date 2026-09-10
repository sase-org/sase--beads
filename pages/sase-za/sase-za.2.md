# Bead: sase-za.2 — Make parked runners cheap

[Bead Pages](../README.md) / [sase-za](README.md) / sase-za.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ih](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ih.md) · **Assignee:** `sase-za.2` · **Size:** medium
**Created:** 2026-09-10 11:44:17 EDT · **Closed:** 2026-09-10 13:49:34 EDT
**Plan:** [202609/host\_resource\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md)

## Description

slot-poll-diet: switch the runner-slot wait loop to the capacity-only scan, share one scan per poll window host-wide under the existing lock, and add jittered backoff with a slot-state change signal while preserving admission semantics.

## Notes

[2026-09-10T17:49:34Z · sase-za.2] Parked runner-slot waiters now use capacity_only scans, share one host-wide cache under runner_slots.lock, and jitter-backoff up to 10x the poll interval until a slot-state token bump (marker mutations, claim/release) resets them. Verified: unit tests for scan reuse, token invalidation, backoff reset, and unchanged-marker retries; existing slot admission tests; just check (lint + full suite after core-identity escalation).

## Dependencies

- **Depends on:** [sase-za.1](sase-za.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-za.4](sase-za.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-za.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.2/README.md) | [sase-za.2](sase-za.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`755ef4a`](https://github.com/sase-org/sase/commit/755ef4a7b60a3bae79072a94b3c8cf4f010f7574) | perf(axe): cheapen parked runner-slot waiters | [sase-za.2](sase-za.2.md) | 2026-09-10 13:50:52 EDT |
