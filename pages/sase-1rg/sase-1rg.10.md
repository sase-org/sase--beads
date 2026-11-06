# Bead: sase-1rg.10 — Record the real actor and skip no-op reopen events in sase-core

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.10` · **Size:** medium
**Created:** 2026-11-06 05:46:52 EST · **Closed:** 2026-11-06 09:21:59 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

open-actor: thread the mutating actor through the core reopen mutation instead of the bead creator, make reopening an already-open bead a no-op, and move the sase-core pin.

## Notes

[2026-11-06T13:27:38Z · sase-1rg.10] PROPOSED FOLLOW-UP: Thread the mutating actor through update, claims, and remove core mutations, which still record issue.created_by as the event actor like open did before this phase

[2026-11-06T14:21:37Z · sase-1rg.10] PROPOSED FOLLOW-UP: just check test-scoped lane fails on tests/test_pytest_isolation_guards.py (test_no_undo_on_shared_monkeypatch_fixture + dependent test_session_sandbox_seal_is_not_first_test) because tests/ace/tui/test_log_panel_keymap.py:331 calls monkeypatch.undo() on the shared fixture; offender file is untouched by this phase and no task bead tracks it yet

[2026-11-06T14:21:59Z · sase-1rg.10] open-actor done and verified. sase-core: run_open records the acting opener (Option<String>, store-owner fallback like close) on every IssueOpened event instead of created_by; reopening an already-open bead is a no-op (no event, no write, changed:false, message set); py_bead_open gains optional author; Rust handle_open prints Already-open on no-op. sase: facade/project.open take author, handle_bead_open resolves it via resolve_mutation_author, skips commit and prints Already-open on no-op, and open is routed off the Rust fast path like create. Tests: 3 new Rust tests in mutation/tests/open.rs pass; 4 open goldens regenerated (justified: phase-mandated actor and no-op change); 15 Python open/guard tests and 70 adjacent tests pass. Gates: sase-core just check passed (tool run dcd80bfc, exit 0, verdict pass). sase just check (tool run c0d0b9aa): 60259 passed, 2 failed, both pre-existing in tests/test_pytest_isolation_guards.py from tests/ace/tui/test_log_panel_keymap.py:331 monkeypatch.undo() (file untouched by this phase; recorded as PROPOSED FOLLOW-UP). PIN PENDING: sase-core-revision.txt still at 417d5c8d; the linked sase-core changes are uncommitted (agents never commit) so the pin must ratchet past the sase-core commit after host finalizers commit+push it — do not land the sase side before the pin moves, since released sase-core-rs lacks the bead_open author param.

## Dependencies

- **Depends on:** [sase-1rg.9](sase-1rg.9.md) ✓ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.10.md) | [sase-1rg.10](sase-1rg.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2815992`](https://github.com/sase-org/sase-core/commit/28159925724bc9ff46c3fccd9047f159f428c861) | feat(bead): thread opener actor through core open mutation | [sase-1rg.10](sase-1rg.10.md) | 2026-11-06 09:28:09 EST |
