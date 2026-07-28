# Bead: sase-7t.1 — Explicit chop-launch linkage scoping

[Bead Pages](../README.md) / [sase-7t](README.md) / sase-7t.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7t.1`
**Created:** 2026-07-19 23:47:02 UTC
**Plan:** [202607/chop\_lifecycle\_fixes\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202607/chop_lifecycle_fixes_v2.md)

## Description

'Explicit chop-launch linkage scoping' section: register chop-agent linkage only for explicit runner launches and continuation respawns, scrub ambient SASE_CHOP_* from unrelated child agents, and isolate the leaking launcher tests from real axe state.

## Notes

COMMIT: 3912356d6

## Dependencies

- **Blocks:** [sase-7t.2](sase-7t.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7t.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7t.1/README.md) | [sase-7t.1](sase-7t.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1790e44`](https://github.com/sase-org/sase/commit/1790e441c2d37b2e61cdd919ca4c5106116af0e6) | fix: scope chop linkage to explicit launches (sase-7t.1) | [sase-7t.1](sase-7t.1.md) | 2026-07-20 00:35:08 |
