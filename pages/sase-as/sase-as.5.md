# Bead: sase-as.5 — Generic sidecar roles in the SDD store

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.5` · **Size:** medium
**Created:** 2026-07-29 14:31:15 UTC · **Closed:** 2026-07-29 15:05:33 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

store-roles: replace the store record's fixed plans/research/beads fields with a role-keyed sidecar map, make `SddStore` resolve roots for any configured role, and stop requiring a sidecar literally named `research` before a sidecar-storage record can be written or considered materialized.

## Notes

[2026-07-29T15:05:33Z · sase-as.5] Implemented role-keyed SDD store records and roots, plans-only materialization, generic sidecar initialization/clone resolution, and commit partitioning for custom roles. Verified 128 focused tests pass; ruff, mypy, Symvision, formatting, and diff checks pass. Full suite: 23,563 passed and 7 skipped; only 5 unrelated AXE PNG snapshot mismatches failed. Full just check was additionally blocked by pre-existing generated-skill drift and three shared plan-link validation errors.

[2026-07-29T15:06:43Z · sase-as.5] Verified 128 focused SDD store tests passed; formatting, ruff, mypy, Symvision, and diff checks passed; full suite completed with 23,563 passed and 7 skipped, with 5 unrelated existing AXE PNG snapshot mismatches.

## Dependencies

- **Blocks:** [sase-as.6](sase-as.6.md) ✓
- **Blocks:** [sase-as.8](sase-as.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.5/README.md) | [sase-as.5](sase-as.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`70a22c3`](https://github.com/sase-org/sase/commit/70a22c347e617988e3a25b62975ab12837ea4444) | feat(sdd): support generic sidecar roles | [sase-as.5](sase-as.5.md) | 2026-07-29 15:07:29 |
