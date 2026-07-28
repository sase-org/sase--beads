# Bead: sase-91.3 — Per-item publication isolation, honest errors, and quarantine

[Bead Pages](../README.md) / [sase-91](README.md) / sase-91.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-91.3` · **Size:** medium
**Created:** 2026-07-24 23:42:03 UTC
**Plan:** [202607/agents\_sidecar\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_sidecar_publication_recovery.md)

## Description

'Phase 3: Per-item publication isolation, honest errors, and quarantine' section: stop head-of-line blocking in the outbox drain, record per-item errors instead of broadcasting one error to every item, and quarantine repeatedly failing items.

## Notes

COMMIT: c2fa0149b

## Dependencies

- **Depends on:** [sase-91.2](sase-91.2.md) ✓
- **Blocks:** [sase-91.6](sase-91.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-91.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-91.3/README.md) | [sase-91.3](sase-91.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7bb485d`](https://github.com/sase-org/sase/commit/7bb485d33f966a4471cd67c59a20b0b4e6c0982e) | fix(agents): quarantine failing publication requests (sase-91.3) | [sase-91.3](sase-91.3.md) | 2026-07-25 01:07:50 |
