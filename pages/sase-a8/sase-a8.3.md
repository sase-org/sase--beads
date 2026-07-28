# Bead: sase-a8.3 — Schema v3 store record and beads kind resolution

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Size:** medium
**Created:** 2026-07-27 19:46:29 UTC · **Closed:** 2026-07-27 20:23:56 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

record: add an optional `beads` sidecar to the SDD store record at schema version 3, resolve `kind_root("beads")` and a per-kind repo root from it, and keep schema-2 records resolving bead state to the plans sidecar unchanged.

## Dependencies

- **Blocks:** [sase-a8.4](sase-a8.4.md) ✓
- **Blocks:** [sase-a8.5](sase-a8.5.md) ✓
- **Blocks:** [sase-a8.6](sase-a8.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.3/README.md) | [sase-a8.3](sase-a8.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f9bd6ad`](https://github.com/sase-org/sase/commit/f9bd6ad226fba1067e1abfd6ae885e3ad312c371) | feat(sdd): support split beads sidecar records (sase-a8.3) | [sase-a8.3](sase-a8.3.md) | 2026-07-27 20:16:40 |
