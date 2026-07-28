# Bead: sase-a1.4 — Stop closing descendants nobody worked

[Bead Pages](../README.md) / [sase-a1](README.md) / sase-a1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a1.4` · **Size:** medium
**Created:** 2026-07-27 16:34:39 UTC · **Closed:** 2026-07-27 17:40:14 UTC
**Plan:** [202607/bead\_history\_truthful\_close.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_history_truthful_close.md)

## Description

invariant: make the parent-close cascade explicit rather than silent — reject a close whose descendants were never closed on their own, require force plus a reason and a non-done resolution to override, record which descendants were swept, and reopen closed ancestors whenever a bead leaves the closed state.

## Dependencies

- **Depends on:** [sase-a1.2](sase-a1.2.md) ✓
- **Blocks:** [sase-a1.6](sase-a1.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a1.4/README.md) | [sase-a1.4](sase-a1.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3deac7d`](https://github.com/sase-org/sase/commit/3deac7d22675315a5adbebe28fd6a2fc4c549241) | feat(bead)!: require explicit descendant close sweeps (sase-a1.4) | [sase-a1.4](sase-a1.4.md) | 2026-07-27 17:44:38 |
