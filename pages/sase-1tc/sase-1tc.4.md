# Bead: sase-1tc.4 — beads.db has one SQLite library owner per process (sase-1kp)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.4` · **Size:** large
**Created:** 2026-11-17 11:19:26 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

beads_db_owner: remove the Rust lock-file and Python WAL-mirror collision on beads.db per the mirror_fix decision, with a same-process repro test.

## Dependencies

- **Depends on:** [sase-1tc.3](sase-1tc.3.md) ◐ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.5](sase-1tc.5.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.4/README.md) | [sase-1tc.4](sase-1tc.4.md) | 0 |
