# Bead: sase-1q4.3 — Keyword-only macro inputs in sase-core

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.3` · **Size:** medium
**Created:** 2026-10-30 17:43:13 EDT · **Closed:** 2026-10-30 23:31:02 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

kwonly_core: add keyword_only to the Rust macro input contract (catalog, wires, frontmatter rules, positional mapping, signatures, gateway contract).

## Notes

[2026-10-30T23:02:12Z · sase-1q4.3--1] PROPOSED FOLLOW-UP: Corroborate existing flake sase-15h: the full sase-core check failed in sudo_runner::tests::worker::output_policy_none_keeps_ledger_empty at result.is_ok(), while that focused test passed alone; this is another parallel fake-sudo fixture failure to triage.

[2026-10-31T01:47:42Z · sase-1q4.3--1] PROPOSED FOLLOW-UP: Avoid quadratic temp-dir allocation in tests/_conftest_environment.py::_isolate_sase_home: the primary scoped check has spent over two hours in pytest TempPathFactory.mktemp("home"), whose popen-gw0 directory currently has 27,816 entries; consider a bounded per-session home allocator and verify check runtime.

[2026-10-31T03:31:02Z · sase-1q4.3--1] Implemented keyword_only across the core macro catalog, editor frontmatter/completion/wires, and mobile gateway; updated the mobile JSON snapshot and authorized macros memory note. Core just fmt passed; core full check had one sudo_runner fixture failure tracked by sase-15h, and the focused test passed alone. Primary just fmt and sase tool run check passed; epic-symbol scan has no leftovers.

## Dependencies

- **Blocks:** [sase-1q4.9](sase-1q4.9.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.3.md) | [sase-1q4.3](sase-1q4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@18ad5fd`](https://github.com/sase-org/sase-core/commit/18ad5fd6f4592af4d61ef8e8187514b032bec03f) | feat(macro): add keyword-only input metadata and binding rules | [sase-1q4.3](sase-1q4.3.md) | 2026-10-30 23:32:07 EDT |
