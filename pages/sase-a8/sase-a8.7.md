# Bead: sase-a8.7 — Lazy beads sidecar materialization

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Size:** medium
**Created:** 2026-07-27 19:47:01 UTC · **Closed:** 2026-07-28 09:42:24 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

lazyclone: make `sase bead` clone the beads sidecar on demand when `sase/repos/beads` is missing, mirroring how `sase repo open` and `--ensure` materialize sidecars.

## Dependencies

- **Blocks:** [sase-a8.10](sase-a8.10.md) ✓
- **Depends on:** [sase-a8.4](sase-a8.4.md) ✓
- **Depends on:** [sase-a8.5](sase-a8.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.7/README.md) | [sase-a8.7](sase-a8.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`73a75f9`](https://github.com/sase-org/sase/commit/73a75f94d4370b0ba582bccfa025f45839f4976f) | feat(beads): materialize split sidecar on demand (sase-a8.7) | [sase-a8.7](sase-a8.7.md) | 2026-07-27 21:31:14 |
