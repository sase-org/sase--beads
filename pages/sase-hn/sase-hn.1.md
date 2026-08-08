# Bead: sase-hn.1 — Establish Patch and stitch terminology in the Rust core

[Bead Pages](../README.md) / [sase-hn](README.md) / sase-hn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vu/README.md) · **Assignee:** `sase-hn.1` · **Size:** medium
**Created:** 2026-08-08 13:05:44 EDT · **Closed:** 2026-08-08 13:22:02 EDT
**Plan:** [202608/patch\_and\_stitch\_terminology.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_and_stitch_terminology.md)

## Description

rust-core-contract: add canonical Rust domain names and parser/wire compatibility while preserving serialized and binding contracts.

## Notes

[2026-08-08T17:22:02Z · sase-hn.1] Verified in sase-core: cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace. Also ran targeted wire/parser/PyO3 tests and git diff --check.

[2026-08-08T17:24:45Z · sase-hn.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, targeted wire/parser/PyO3 tests, and git diff --check.

## Dependencies

- **Blocks:** [sase-hn.2](sase-hn.2.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.1/README.md) | [sase-hn.1](sase-hn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8344869`](https://github.com/sase-org/sase-core/commit/83448690a9c54b4342482d66c1e843d290c4564d) | feat(core): add Patch and stitch wire contract | [sase-hn.1](sase-hn.1.md) | 2026-08-08 13:36:43 EDT |
