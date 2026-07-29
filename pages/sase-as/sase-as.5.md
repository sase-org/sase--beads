# Bead: sase-as.5 — Generic sidecar roles in the SDD store

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.5

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.5` · **Size:** medium
**Created:** 2026-07-29 14:31:15 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

store-roles: replace the store record's fixed plans/research/beads fields with a role-keyed sidecar map, make `SddStore` resolve roots for any configured role, and stop requiring a sidecar literally named `research` before a sidecar-storage record can be written or considered materialized.

## Dependencies

- **Blocks:** [sase-as.6](sase-as.6.md) ◐
- **Blocks:** [sase-as.8](sase-as.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.5/README.md) | [sase-as.5](sase-as.5.md) | 0 |
