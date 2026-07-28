# Bead: sase-8g.11 — Keep tests out of production state

[Bead Pages](../README.md) / [sase-8g](README.md) / sase-8g.11

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8g.11` · **Size:** medium
**Created:** 2026-07-20 20:31:46 UTC
**Plan:** [202607/audit\_24h\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202607/audit_24h_fixes.md)

## Description

'Keep tests out of production state' section: guard telemetry and notification writers against unisolated pytest runs so test fixtures stop polluting the real metrics DB and axe logs.

## Notes

COMMIT: 231b77e

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8g.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8g.11/README.md) | [sase-8g.11](sase-8g.11.md) | 1 |
| [bbugyi200.athena.sase-8g.11--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8g.11.md#member-code) | [sase-8g.11](sase-8g.11.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`866aea6`](https://github.com/sase-org/sase/commit/866aea65a3fc91224db3382125e71fd3494bcd70) | feat(telemetry): isolate test state and add cleanup command (sase-8g.11) | [sase-8g.11](sase-8g.11.md) | 2026-07-20 21:41:49 |
