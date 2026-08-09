# Bead: sase-i9.2 — Build the Rust core and LSP in one feature-unified cargo invocation

[Bead Pages](../README.md) / [sase-i9](README.md) / sase-i9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wj/README.md) · **Assignee:** `sase-i9.2` · **Size:** medium
**Created:** 2026-08-09 10:10:48 EDT · **Closed:** 2026-08-09 11:32:41 EDT
**Plan:** [202608/fast\_dev\_update.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_dev_update.md)

## Description

unified-build: collapse the two separate cargo/maturin reconcile steps into a single feature-unified build so sase_core and its shared dependencies compile once per update instead of twice, and so the two builds stop invalidating each other's cached units.

## Notes

[2026-08-09T15:31:43Z · sase-i9.2] PROPOSED FOLLOW-UP: Revisit true single Cargo build packaging - maturin 1.14 still reruns cargo rustc after a feature-unified cargo build, so this phase shipped target-dir isolation instead.

[2026-08-09T15:32:41Z · sase-i9.2] Implemented rust_dev_install dev-update reconcile step with just rust-dev-install-uv-tool and sase-core extension-module passthrough. Measured feature-unified cargo build 188.15s followed by maturin rebuild 99.20s, so shipped Plan B target-dir isolation (target/uv-tool-py and target/uv-tool-lsp). Verified cold recipe after cargo clean 408.28s; warm recipe 2.08s with maturin 0.19s and LSP cargo 0.16s. Tests passed: focused pytest dev_update/update_command, cargo test --workspace, just rust-test, just check.

[2026-08-09T15:34:32Z · sase-i9.2] Verified focused pytest (37 passed), cargo test --workspace, just rust-test, just check, cold rust-dev-install-uv-tool at 408.28s, and warm rust-dev-install-uv-tool at 2.08s.

## Dependencies

- **Depends on:** [sase-i9.1](sase-i9.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.3](sase-i9.3.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.4](sase-i9.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.5](sase-i9.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i9.2/README.md) | [sase-i9.2](sase-i9.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1a96264`](https://github.com/sase-org/sase-core/commit/1a962643d9ef7d0c86e7bba64e3ccd1a167532a2) | build: expose extension-module feature for PyO3 crate | [sase-i9.2](sase-i9.2.md) | 2026-08-09 11:36:21 EDT |
| sase | [`d83fe96`](https://github.com/sase-org/sase/commit/d83fe9668c0bd70b15d16ec87be0dbc03b8156b4) | perf: install Rust dev artifacts in one update step | [sase-i9.2](sase-i9.2.md) | 2026-08-09 11:38:02 EDT |
