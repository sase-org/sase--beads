# Bead: sase-93.2 — Stop \`install\_tui\_file\_logging\` from leaking the \`sase\` logger level into other tests

[Bead Pages](../README.md) / [sase-93](README.md) / sase-93.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-93.2` · **Size:** small
**Created:** 2026-07-25 11:27:12 UTC · **Closed:** 2026-07-25 11:36:15 UTC
**Plan:** [202607/restore\_green\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202607/restore_green_ci.md)

## Description

'Phase: keymap-log-level' section: restore the `sase` logger level in the TUI log-setup fixture and scope the keymap registry test's caplog to the emitting logger.

## Notes

COMMIT: 50e3d73ec

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-93.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-93.2/README.md) | [sase-93.2](sase-93.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`50e3d73`](https://github.com/sase-org/sase/commit/50e3d73ecee0429ee5ed7d04130fbf08aa866245) | test: stop TUI log setup from leaking the \`sase\` logger level (sase-93.2) | [sase-93.2](sase-93.2.md) | 2026-07-25 11:37:14 |
