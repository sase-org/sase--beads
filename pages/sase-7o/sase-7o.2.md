# Bead: sase-7o.2 — Replace %tribe with the tribe= kwarg and add

[Bead Pages](../README.md) / [sase-7o](README.md) / sase-7o.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7o.2`
**Created:** 2026-07-19 19:41:47 UTC
**Plan:** [202607/id\_kwargs\_tribe\_family.md](https://github.com/sase-org/sase--plans/blob/main/202607/id_kwargs_tribe_family.md)

## Description

'Phase 2: Replace %tribe with the tribe= kwarg and add #tribe' section: remove %tribe|%t behind a migration error, parse %id(..., tribe=<t>) into the tag flow with an implicit auto id when the positional is omitted, migrate the TUI tag modal, retry rewrites, and axe chop emitter, ship the built-in #tribe xprompt, and update completion, docs, skill sources, and tests.

## Notes

COMMIT: 3f41c7c81

## Dependencies

- **Depends on:** [sase-7o.1](sase-7o.1.md) ✓
- **Blocks:** [sase-7o.3](sase-7o.3.md) ✓
- **Blocks:** [sase-7o.4](sase-7o.4.md) ✓
- **Blocks:** [sase-7o.5](sase-7o.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7o.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7o.2/README.md) | [sase-7o.2](sase-7o.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3f41c7c`](https://github.com/sase-org/sase/commit/3f41c7c81a9ae5da291717e3f16994775b6a86ba) | feat!: fold tribe assignment into id kwargs (sase-7o.2) | [sase-7o.2](sase-7o.2.md) | 2026-07-19 21:31:42 |
