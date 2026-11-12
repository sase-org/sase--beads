# Bead: sase-1sb.7 — Chat-catalog cache lock handling and bead migration idempotency

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.7` · **Size:** small
**Created:** 2026-11-11 17:38:54 EST · **Closed:** 2026-11-11 20:00:14 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

Two verified sqlite defects:

1. src/sase/history/chat_catalog_provenance/cache.py `open_catalog_cache`
   (~lines 30-48): the rebuild path catches `sqlite3.DatabaseError` —
   but `sqlite3.OperationalError` ("database is locked") is a subclass, and
   `_connect` uses a short busy timeout, so plain cross-process contention is
   misdiagnosed as corruption and `_discard_broken_cache` unlinks a database
   another process has open mid-transaction (its commit lands on the orphaned
   inode and is lost; both processes then pay a full head rescan). Fix: treat
   lock contention as transient — re-raise or retry `sqlite3.OperationalError`
   lock errors (match the "database is locked" family, or check
   `sqlite3.DatabaseError and not OperationalError` plus the
   malformed/not-a-database messages) and only discard on genuine corruption;
   consider raising the busy timeout. Add a regression test: hold a write
   transaction from one connection, open the cache from another, and assert the
   db file is NOT unlinked and the second open either waits or fails without
   destroying state.

2. src/sase/bead/_db_migrations.py `_migrate_issue_types` (~lines 224-270): in
   sqlite3 legacy autocommit mode the `CREATE TABLE _issues_new` DDL commits
   immediately while the following INSERT...SELECT opens the implicit
   transaction. If the INSERT fails (legacy row violating the new CHECKs) or the
   process dies before `conn.commit()`, `_issues_new` persists while the guard
   (`"'plan'" in create_table_sql` of `issues`) still reports "not migrated" —
   so every subsequent `init_db` raises "table _issues_new already exists" and
   the bead mirror is wedged until manual repair. Fix: `DROP TABLE IF EXISTS
   _issues_new` before the CREATE so the rebuild is restartable; audit the other
   table-rebuild migrations in the same file for the same pattern and apply the
   same guard where missing. Also make `init_db` (src/sase/bead/db.py ~lines
   28-40) close its connection when `run_migrations` raises (try/finally or
   closing contextmanager). Tests: simulate the half-migrated state (create
   `_issues_new`, keep old-schema `issues`) and assert init_db now completes the
   migration; assert no connection leak on a failing migration (e.g. monkeypatch
   a migration to raise and assert the connection is closed).

## Notes

[2026-11-12T00:59:59Z · sase-1sb.7] PROPOSED FOLLOW-UP: sase-core issue_type_migration_sql still lacks DROP TABLE IF EXISTS _issues_new — later rebuilds in crates/sase_core/src/bead/schema.rs already have the guard; this phase fixed the Python compatibility copy in src/sase/bead/_db_migrations.py.

[2026-11-12T01:00:14Z · sase-1sb.7] Chat-catalog cache re-raises sqlite3.OperationalError lock errors instead of unlinking and uses a 5s busy timeout. _migrate_issue_types drops leftover _issues_new before CREATE so a half-migrated mirror is restartable. init_db closes the connection when run_migrations raises. Other Python table-rebuilds already DROP via Rust SQL. Verified: exclusive-lock open does not unlink the cache; leftover _issues_new no longer wedges init_db; failing migration closes the sqlite connection; corrupt cache still rebuilds. No --epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.7.md) | [sase-1sb.7](sase-1sb.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9572a8`](https://github.com/sase-org/sase/commit/b9572a8d59b73123199c256c7da7be473bf41ccb) | fix(history): keep catalog cache on lock and make bead type migration restartable | [sase-1sb.7](sase-1sb.7.md) | 2026-11-11 21:18:13 EST |
