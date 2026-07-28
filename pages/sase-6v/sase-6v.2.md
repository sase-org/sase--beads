# Bead: sase-6v.2 — Script-only chops with full-name resolution

[Bead Pages](../README.md) / [sase-6v](README.md) / sase-6v.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6v.2`
**Created:** 2026-07-18 19:41:44 UTC
**Plan:** [202607/chops\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/chops_redesign.md)

## Description

'Script-only chops with full-name resolution' section: delete the agent-chop variant, resolve chop scripts by their full configured name with no sase_chop_ prefixing, and make axe config loading fail closed through the new core validation.

## Notes

COMMIT: a7eb30b6c

## Dependencies

- **Depends on:** [sase-6v.1](sase-6v.1.md) ✓
- **Blocks:** [sase-6v.3](sase-6v.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6v.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6v.2/README.md) | [sase-6v.2](sase-6v.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8e4002b`](https://github.com/sase-org/sase/commit/8e4002bb4dd62d15bf8bf604c510fc517eeb0b90) | feat(axe)!: make chops script-only (sase-6v.2) | [sase-6v.2](sase-6v.2.md) | 2026-07-18 21:08:56 |
