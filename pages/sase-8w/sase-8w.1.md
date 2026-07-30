# Bead: sase-8w.1 — Core phase-size support in sase-core

[Bead Pages](../README.md) / [sase-8w](README.md) / sase-8w.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8w.1` · **Size:** medium
**Created:** 2026-07-23 21:38:14 UTC
**Plan:** [202607/phase\_sizes.md](https://github.com/sase-org/sase--plans/blob/main/202607/phase_sizes.md)

## Description

'Core phase-size support in sase-core' section: extend the Rust PhaseSizeWire enum, deserialization, plan validation, schema CHECK constraint + relax migration, and the two schema descriptions to accept xsmall/xlarge.

## Notes

COMMIT: f9d9c37

## Dependencies

- **Blocks:** [sase-8w.3](sase-8w.3.md) ✓
- **Blocks:** [sase-8w.5](sase-8w.5.md) ✓
- **Blocks:** [sase-8w.6](sase-8w.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8w.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8w.1/README.md) | [sase-8w.1](sase-8w.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@f9d9c37`](https://github.com/sase-org/sase-core/commit/f9d9c37a452602a9021c5170892e94346f302390) | feat: support xsmall and xlarge phase sizes (sase-8w.1) | [sase-8w.1](sase-8w.1.md) | 2026-07-23 21:51:06 |
