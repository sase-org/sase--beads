# Bead: sase-x7.2.1.1 — Land the migration wire contract and bindings in the Rust core

[Bead Pages](../README.md) / [sase-x7.2.1](sase-x7.2.1.md) / sase-x7.2.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) · **Assignee:** `sase-x7.2.1.1` · **Size:** medium
**Created:** 2026-09-05 19:32:04 EDT
**Plan:** [202609/migration\_kit.md](https://github.com/sase-org/sase--plans/blob/main/202609/migration_kit.md)

## Description

kit-contract: Add a temporary `migration` module to sase_core (manifest and journal wire types, tree digests, semantic fingerprints, residue classification, procs reconciliation), expose it through sase_core_py, land it, publish a core release exposing the new bindings, then bump the host's sase-core-rs floor and ratchet the pinned revision.

## Notes

[2026-09-06T00:29:45Z · sase-x7.2.1.1] PROPOSED FOLLOW-UP: Publish migration bindings release barrier -- migration wire contract and PyO3 bindings are implemented and verified locally, but PyPI latest sase-core-rs==0.32.24 and tag v0.32.24 (118bb74) do not contain the migration_* bindings; host floor/pin were not bumped, and just check passes only with the expected blocked_unpublished advisory until a new core release exposes them.

## Dependencies

- **Blocks:** [sase-x7.2.1.2](sase-x7.2.1.2.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.1/README.md) | [sase-x7.2.1.1](sase-x7.2.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13ebfeb`](https://github.com/sase-org/sase/commit/13ebfeb061db13fbcc2bea86a83727da6f8398ef) | test(core): require migration bindings in floor checks | [sase-x7.2.1.1](sase-x7.2.1.1.md) | 2026-09-05 20:31:29 EDT |
