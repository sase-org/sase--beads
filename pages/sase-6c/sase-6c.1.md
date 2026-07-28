# Bead: sase-6c.1 — Move pump-blocking async refresh callbacks onto free-standing loop tasks

[Bead Pages](../README.md) / [sase-6c](README.md) / sase-6c.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6c.1`
**Created:** 2026-07-16 15:13:18 UTC
**Plan:** [202607/tui\_pump\_stalls\_and\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202607/tui_pump_stalls_and_startup.md)

## Description

Phase `pump` in approved epic plan `sase/repos/plans/202607/tui_pump_stalls_and_startup.md`.

## Notes

COMMIT: 5579712fd

## Dependencies

- **Blocks:** [sase-6c.5](sase-6c.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6c.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6c.1/README.md) | [sase-6c.1](sase-6c.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0d33d2a`](https://github.com/sase-org/sase/commit/0d33d2a8c71f0a175afb7fbc1163f7499c1ad93e) | perf(tui): move slow refresh work off the message pump (sase-6c.1) | [sase-6c.1](sase-6c.1.md) | 2026-07-16 15:49:02 |
