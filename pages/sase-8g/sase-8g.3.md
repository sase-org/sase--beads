# Bead: sase-8g.3 — Fix runner-slot wait regressions

[Bead Pages](../README.md) / [sase-8g](README.md) / sase-8g.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8g.3` · **Size:** medium
**Created:** 2026-07-20 20:31:22 UTC
**Plan:** [202607/audit\_24h\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202607/audit_24h_fixes.md)

## Description

'Fix runner-slot wait regressions' section: make Run Now actually release parked slot waiters, preserve wait priority across question-yield requeue, and stop the slot poll from clobbering foreign waiting-marker keys.

## Notes

COMMIT: c67001657

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8g.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8g.3/README.md) | [sase-8g.3](sase-8g.3.md) | 1 |
| [bbugyi200.athena.sase-8g.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8g.3.md#member-code) | [sase-8g.3](sase-8g.3.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9aed7d7`](https://github.com/sase-org/sase/commit/9aed7d72366ab5bbf243320fb3c621be21d6eea3) | fix(runner-slots): preserve waiter state across admission (sase-8g.3) | [sase-8g.3](sase-8g.3.md) | 2026-07-20 21:01:23 |
