# Bead: sase-qw.2 — Registered errors and error-anchored launch logs

[Bead Pages](../README.md) / [sase-qw](README.md) / sase-qw.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07n.md) · **Assignee:** `sase-qw.2` · **Size:** medium
**Created:** 2026-08-19 09:29:49 EDT · **Closed:** 2026-08-19 12:39:10 EDT
**Plan:** [202608/last\_error\_log\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/last_error_log_jump.md)

## Description

registry: stamp every launch-failure log entry with a stable error id, add the session-scoped registered-error pointer, make one helper both register the error and emit its toast so the chord hint can never appear without a target, and make `,L` select the registered error's log source.

## Notes

[2026-08-19T16:38:31Z · sase-qw.2] PROPOSED FOLLOW-UP: Re-keyed stale sase-qt.6/sase-qt.7 --epic-symbol Memory* whitelist entries to parent sase-qt after those phases closed — sase-qt.land should drop them once the symbols have non-test consumers.

[2026-08-19T16:38:34Z · sase-qw.2] PROPOSED FOLLOW-UP: sase init memory --check is red on this tree because the installed feature task-type spec digest drifted — run sase memory init only with explicit user permission.

[2026-08-19T16:39:10Z · sase-qw.2] Stamped launch-failure JSONL/human logs with a stable error_id, added session RegisteredError pointer plus notify_registered_error (hint and target are one call), rewired the seven launch/chop sites, and made ,L open Logs with the registered error's source selected. 95 targeted tests passed; just _lint-symvision passed; sase bead epic-symbols sase-qw.2 reported no leftovers for this phase.

[2026-08-19T16:40:47Z · sase-qw.2] Stamped launch-failure JSONL/human logs with a stable error_id, added session RegisteredError pointer plus notify_registered_error (hint and target are one call), rewired the seven launch/chop sites, and made ,L open Logs with the registered error's source selected. 95 targeted tests passed; just _lint-symvision passed; sase bead epic-symbols sase-qw.2 reported no leftovers for this phase.

## Dependencies

- **Depends on:** [sase-qw.1](sase-qw.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qw.3](sase-qw.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qw.2/README.md) | [sase-qw.2](sase-qw.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`422c8c2`](https://github.com/sase-org/sase/commit/422c8c2c57ad248a4e12e34c3e144eeb85ffb358) | feat(logs): stamp launch failures with a session error id | [sase-qw.2](sase-qw.2.md) | 2026-08-19 12:42:26 EDT |
