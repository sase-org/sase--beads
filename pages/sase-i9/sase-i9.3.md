# Bead: sase-i9.3 — Add a fast dev-update cargo profile

[Bead Pages](../README.md) / [sase-i9](README.md) / sase-i9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wj/README.md) · **Assignee:** `sase-i9.3` · **Size:** medium
**Created:** 2026-08-09 10:11:04 EDT · **Closed:** 2026-08-09 12:44:37 EDT
**Plan:** [202608/fast\_dev\_update.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_dev_update.md)

## Description

fast-profile: add a dev-update-only cargo profile in sase-core that drops LTO and codegen-units=1 in favor of incremental parallel codegen, wire the dev-update recipes to it with an escape hatch, and prove the published wheel/CI profile is untouched and runtime performance does not regress.

## Notes

[2026-08-09T16:44:37Z · sase-i9.3] Implemented dev-update Rust profile and SASE_RUST_DEV_PROFILE env path; verified cargo metadata, just install release profile 3m42s, cold rust-dev-install-uv-tool 3:09.22 wall with dev-update profile (py 1m37s, lsp 1m30s), warm 1.516s (py 0.08s, lsp 0.09s), uv-tool import/LSP artifacts, just rust-test, TUI perf bench 5 passed, targeted pytest 53 passed, just check, and just check-full.

[2026-08-09T16:46:14Z · sase-i9.3] Implemented dev-update cargo profile wiring, env override plumbing, docs/tests, and verified just install, cold/warm rust-dev-install-uv-tool, just rust-test, TUI perf benchmark, targeted pytest, just check, and just check-full.

## Dependencies

- **Depends on:** [sase-i9.2](sase-i9.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.4](sase-i9.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.5](sase-i9.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i9.3/README.md) | [sase-i9.3](sase-i9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d6e3ea2`](https://github.com/sase-org/sase-core/commit/d6e3ea299f9ddfe2412fb11571c241f66712fb5d) | perf: add dev-update cargo profile | [sase-i9.3](sase-i9.3.md) | 2026-08-09 12:47:51 EDT |
