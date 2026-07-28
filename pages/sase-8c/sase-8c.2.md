# Bead: sase-8c.2 — Parse %wait(priority=...) and make admission priority-aware

[Bead Pages](../README.md) / [sase-8c](README.md) / sase-8c.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8c.2` · **Size:** medium
**Created:** 2026-07-20 18:11:04 UTC · **Closed:** 2026-07-20 18:49:02 UTC
**Plan:** [202607/wait\_priority\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202607/wait_priority_directive.md)

## Description

'SASE: %wait(priority=...) directive and priority-aware admission' section: parse and validate the new keyword, thread it through agent meta and the waiting marker, sort the runner-slot queue by priority ahead of wait time, and cover parsing, admission, locked-gate, and fakey e2e tests.

## Notes

COMMIT: 5cb38776f

## Dependencies

- **Depends on:** [sase-8c.1](sase-8c.1.md) ✓
- **Blocks:** [sase-8c.3](sase-8c.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8c.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8c.2/README.md) | [sase-8c.2](sase-8c.2.md) | 1 |
| [bbugyi200.athena.sase-8c.2--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8c.2.md#member-code) | [sase-8c.2](sase-8c.2.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`46c2f06`](https://github.com/sase-org/sase/commit/46c2f0622a4998cf01e997a147df5c600ee1bae7) | feat: prioritize runner-slot wait admission (sase-8c.2) | [sase-8c.2](sase-8c.2.md) | 2026-07-20 18:49:41 |
