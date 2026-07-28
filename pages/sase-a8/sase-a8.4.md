# Bead: sase-a8.4 — Beads sidecar registration and inventory

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a8.4` · **Size:** medium
**Created:** 2026-07-27 19:46:38 UTC · **Closed:** 2026-07-27 20:41:56 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

config: register `beads` as a managed sidecar role across defaults, identity, clone-dir mapping, repo inventory, `sase repo path`, doctor storage checks, and the config schema, gating auto-clone on a recorded beads sidecar.

## Notes

[2026-07-27T20:41:45Z · sase-a8.4] Implemented first-class beads sidecar registration across defaults, identity and clone-dir resolution, inventory, repo-init config, repo path, doctor regression checks, schema docs, and project config. Auto-clone is gated on a recorded beads sidecar. Verification: 95 focused tests passed; full suite reached 22,790 passed and 7 skipped with one xdist-only AF_UNIX path-too-long failure that passed standalone; formatting and all lint layers passed. just check stops only at the expected interim init repo --check action to create the unmaterialized beads sidecar and README, owned by later epic phases.

## Dependencies

- **Depends on:** [sase-a8.3](sase-a8.3.md) ✓
- **Blocks:** [sase-a8.7](sase-a8.7.md) ✓
- **Blocks:** [sase-a8.8](sase-a8.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.4/README.md) | [sase-a8.4](sase-a8.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c113156`](https://github.com/sase-org/sase/commit/c113156466bd746064212cfe48e80fc74073ffe3) | feat: register beads as a managed sidecar (sase-a8.4) | [sase-a8.4](sase-a8.4.md) | 2026-07-27 20:43:42 |
