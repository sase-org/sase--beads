# Bead: sase-be.1 — List-valued output variables in the sase-core scan wire

[Bead Pages](../README.md) / [sase-be](README.md) / sase-be.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-be.1` · **Size:** medium
**Created:** 2026-07-30 20:05:57 UTC · **Closed:** 2026-07-30 20:15:52 UTC
**Plan:** [202607/commit\_vars\_finalizer.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_vars_finalizer.md)

## Description

list-vars-rust: extend the Rust agent-scan wire and scanner coercion in the sase-core repo so output variables carry string-or-list-of-string values, with parity tests and a released version bump.

## Notes

[2026-07-30T20:15:52Z · sase-be.1] Implemented OutputVariableValue::Text/List in the sase-core agent-scan wire, dedicated strict string-or-all-string-list scanner coercion, public re-exports, and parity cases for ordered/empty lists plus rejected mixed, nested, object, and numeric values. Verified targeted agent_scan_parity test, cargo fmt --all -- --check, cargo test --workspace, and cargo clippy --workspace --all-targets -- -D warnings with only the two unrelated Rust 1.97 lint drifts allowed (question_mark in bead/read.rs:232 and needless_borrow in bead_read_parity.rs:594). Cargo versions remain release-plz-owned as required; no manual version fields were edited.

## Dependencies

- **Blocks:** [sase-be.2](sase-be.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-be.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-be.1/README.md) | [sase-be.1](sase-be.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@3fdffb2`](https://github.com/sase-org/sase-core/commit/3fdffb27c2b0d024caf55454bb4c81adbd903cce) | feat(agent-scan)!: preserve list-valued output variables | [sase-be.1](sase-be.1.md) | 2026-07-30 20:17:33 |
