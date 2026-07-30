# Bead: sase-ba.1 — Rust core: store economics, retention planner, and trash primitives

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.1` · **Size:** medium
**Created:** 2026-07-30 14:39:48 UTC · **Closed:** 2026-07-30 15:06:47 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

core-lifecycle: add a pure store-economics aggregator, a pure retention planner, and clock-free trash store/list/restore/purge primitives to `sase_core`, expose all four through `sase_core_rs`, and release the crate.

## Notes

[2026-07-30T15:06:47Z · sase-ba.1] Implemented artifact lifecycle wire schema v1 with pure store economics, deterministic retention planning, clock-free restorable trash store/list/restore/purge primitives, and all six PyO3 lifecycle bindings. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace (1091 core tests plus all workspace integration suites), git diff --check, local just install, sase core health, and Python schema/export probes. Parent just check passed formatting and all lint gates, then stopped only on unrelated existing plans-sidecar missing prompt-link validation errors.

## Dependencies

- **Blocks:** [sase-ba.2](sase-ba.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.1/README.md) | [sase-ba.1](sase-ba.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@95f8440`](https://github.com/sase-org/sase-core/commit/95f8440f4212c272be32a967c98b34784d05e56b) | feat: add artifact store lifecycle primitives | [sase-ba.1](sase-ba.1.md) | 2026-07-30 15:09:03 |
