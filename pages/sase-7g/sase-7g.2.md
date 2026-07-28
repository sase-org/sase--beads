# Bead: sase-7g.2 — Add the clan= kwarg to %id

[Bead Pages](../README.md) / [sase-7g](README.md) / sase-7g.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7g.2`
**Created:** 2026-07-19 16:05:02 UTC
**Plan:** [202607/id\_directive\_clan\_kwarg.md](https://github.com/sase-org/sase--plans/blob/main/202607/id_directive_clan_kwarg.md)

## Description

'Phase 2: Add the clan= kwarg to %id' section: parse %id(<id>, clan=<clan>), derive the <clan>.<id> agent name, add the clan-membership flags to PromptDirectives, and enforce the new directive-combination validation errors.

## Notes

COMMIT: 453d6833c

## Dependencies

- **Depends on:** [sase-7g.1](sase-7g.1.md) ✓
- **Blocks:** [sase-7g.3](sase-7g.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7g.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7g.2/README.md) | [sase-7g.2](sase-7g.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`985b1c0`](https://github.com/sase-org/sase/commit/985b1c0d1dbd20c91d473b5d19283bb56c28cfbe) | feat: support clan-scoped agent IDs (sase-7g.2) | [sase-7g.2](sase-7g.2.md) | 2026-07-19 17:50:21 |
