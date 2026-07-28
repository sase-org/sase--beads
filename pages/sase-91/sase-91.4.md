# Bead: sase-91.4 — Single-inventory drain and lock-time reduction

[Bead Pages](../README.md) / [sase-91](README.md) / sase-91.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-91.4` · **Size:** medium
**Created:** 2026-07-24 23:42:06 UTC
**Plan:** [202607/agents\_sidecar\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_sidecar_publication_recovery.md)

## Description

'Phase 4: Single-inventory drain and lock-time reduction' section: build the project inventory once per drain, deduplicate queued hoods, stop the permanently-stale name-registry rebuild, and reduce work done while holding the sidecar lock.

## Notes

COMMIT: 4be81e0f3

## Dependencies

- **Depends on:** [sase-91.2](sase-91.2.md) ✓
- **Blocks:** [sase-91.6](sase-91.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-91.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-91.4/README.md) | [sase-91.4](sase-91.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1449c9b`](https://github.com/sase-org/sase/commit/1449c9bb7b46348f391ffdbb8fffdd6d5a38384d) | perf(agents-sync): reduce publication drain lock work (sase-91.4) | [sase-91.4](sase-91.4.md) | 2026-07-25 00:56:13 |
