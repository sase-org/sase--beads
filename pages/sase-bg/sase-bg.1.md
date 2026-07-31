# Bead: sase-bg.1 — Rust core task type, ready status, and ready-query redefinition

[Bead Pages](../README.md) / [sase-bg](README.md) / sase-bg.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bg.1` · **Size:** medium
**Created:** 2026-07-30 22:55:18 UTC · **Closed:** 2026-07-30 23:11:44 UTC
**Plan:** [202607/task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202607/task_beads.md)

## Description

core-model: add IssueTypeWire::Task and StatusWire::Ready with validation, schema CHECKs and migrations, redefine the ready query to unblocked ready task beads, extend CLI parse/render/stats tables, and cover with parity and mutation tests in the sase-core linked repo.

## Notes

[2026-07-30T23:11:44Z · sase-bg.1] Implemented the Rust core task bead type and ready status, validation and SQLite migration checks, ready-task query semantics, CLI/search/stats rendering, and Rust/Python parity coverage in the sase-core linked repo. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace; all passed.

## Dependencies

- **Blocks:** [sase-bg.2](sase-bg.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bg.1/README.md) | [sase-bg.1](sase-bg.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@2e3ff72`](https://github.com/sase-org/sase-core/commit/2e3ff7293926aedac27af4fa5f471a7a93fc1884) | feat(bead)!: add task beads and ready workflow | [sase-bg.1](sase-bg.1.md) | 2026-07-30 23:13:22 |
