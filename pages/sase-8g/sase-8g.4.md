# Bead: sase-8g.4 — Degrade TUI axe status gracefully

[Bead Pages](../README.md) / [sase-8g](README.md) / sase-8g.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8g.4` · **Size:** small
**Created:** 2026-07-20 20:31:24 UTC
**Plan:** [202607/audit\_24h\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202607/audit_24h_fixes.md)

## Description

'Degrade TUI axe status gracefully' section: surface invalid axe config as a status instead of raising every auto-refresh tick, and dedupe repeated pump-task failure logs.

## Notes

COMMIT: 62684a7db

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8g.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8g.4/README.md) | [sase-8g.4](sase-8g.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`47f6df2`](https://github.com/sase-org/sase/commit/47f6df24b96976ef4228910abc20182c77755372) | fix(tui): degrade invalid axe status gracefully (sase-8g.4) | [sase-8g.4](sase-8g.4.md) | 2026-07-20 20:48:33 |
