# Bead: sase-8w.3 — Python phase-size domain and prompt routing

[Bead Pages](../README.md) / [sase-8w](README.md) / sase-8w.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8w.3` · **Size:** medium
**Created:** 2026-07-23 21:38:19 UTC
**Plan:** [202607/phase\_sizes.md](https://github.com/sase-org/sase--plans/blob/main/202607/phase_sizes.md)

## Description

'Python phase-size domain and prompt routing' section: add XSMALL/XLARGE to the Python PhaseSize enum and route them through work.py size->alias mapping and phase_requires_plan, the bead wire (de)serialization, DB load, and the CLI --size choices.

## Notes

COMMIT: a5c5d0398

## Dependencies

- **Depends on:** [sase-8w.1](sase-8w.1.md) ✓
- **Depends on:** [sase-8w.2](sase-8w.2.md) ✓
- **Blocks:** [sase-8w.4](sase-8w.4.md) ✓
- **Blocks:** [sase-8w.5](sase-8w.5.md) ✓
- **Blocks:** [sase-8w.6](sase-8w.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8w.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8w.3/README.md) | [sase-8w.3](sase-8w.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a5c5d03`](https://github.com/sase-org/sase/commit/a5c5d0398e31032622ca93624fddc95d8a1bcc58) | feat(bead): support extended phase sizes (sase-8w.3) | [sase-8w.3](sase-8w.3.md) | 2026-07-23 22:18:40 |
