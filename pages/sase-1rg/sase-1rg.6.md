# Bead: sase-1rg.6 — Keep reserved joined runs alive through staged adoption

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.6` · **Size:** medium
**Created:** 2026-11-06 05:46:50 EST · **Closed:** 2026-11-06 07:28:36 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

staged-join: stop the end-of-turn cleanup and starter watchdog from stopping tool runs that a staged monitor has reserved, and fall back to a fresh owned run when a joined run is gone at adoption.

## Notes

[2026-11-06T12:28:36Z · sase-1rg.6] Protected live staged-join reservations in cleanup and the starter watchdog; adoption now reacquires unusable joined runs and persists the replacement run/label. Verified with sase tool run check (passed) and no remaining epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1rg.8](sase-1rg.8.md) ◐ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.6/README.md) | [sase-1rg.6](sase-1rg.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c65055e`](https://github.com/sase-org/sase/commit/c65055eff66b1cc47d95a2855df7db264a2c862f) | fix(monitor): preserve staged joined tool runs | [sase-1rg.6](sase-1rg.6.md) | 2026-11-06 07:31:10 EST |
