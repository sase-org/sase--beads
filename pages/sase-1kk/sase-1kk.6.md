# Bead: sase-1kk.6 — Regression guard, ownership docs, and follow-ups

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.6` · **Size:** small
**Created:** 2026-10-13 12:24:29 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

guard: add a static test that forbids stdlib sqlite3 connections outside an allowlist of Python-owned databases, document SQLite ownership, and record follow-ups for the remaining CLI-only hazards.

## Notes

[2026-10-13T22:06:50Z · sase-1kk.6] PROPOSED FOLLOW-UP: beads.db dual-use — Rust uses beads.db as its mutation lock file (sase-core bead/mutation store_lock.rs opens/closes it per mutation, dropping POSIX locks) while Python keeps it as a WAL SQLite mirror via BeadProjectStoreMixin._conn_cache (src/sase/bead/_project_store.py); CLI-only today through the compatibility mirror, needs a single-owner plan

[2026-10-13T22:06:55Z · sase-1kk.6] PROPOSED FOLLOW-UP: migration_kit opens arbitrary live databases incl. Rust-owned ones with stdlib sqlite3 (src/sase/migration_kit/sqlite_backup.py backup_sqlite_file, reached from backup.py for every SQLite-looking file under the declared root), reads headers with plain open() (looks_like_sqlite_file), and hashes live DB bytes (restore.py/hash live paths); all CLI-only, needs binding-based or quiesced handling

## Dependencies

- **Depends on:** [sase-1kk.4](sase-1kk.4.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kk.5](sase-1kk.5.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kk.6.md) | [sase-1kk.6](sase-1kk.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`73a61e6`](https://github.com/sase-org/sase/commit/73a61e694495691e2add372947503aa4151adba2) | test(sqlite): guard single-library ownership and document it | [sase-1kk.6](sase-1kk.6.md) | 2026-10-13 18:18:11 EDT |
