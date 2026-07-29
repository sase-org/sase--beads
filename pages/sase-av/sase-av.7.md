# Bead: sase-av.7 — Artifact-reference completion and diagnostics in the xprompt LSP

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.7` · **Size:** large
**Created:** 2026-07-29 16:48:37 UTC · **Closed:** 2026-07-29 19:00:08 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

lsp-complete: complete and diagnose artifact references in the Rust xprompt LSP server, fed by a launcher-materialized artifact catalog, mirroring the prompt bar's recognition and known-kind rules so editors and the TUI agree on what a reference means.

## Notes

[2026-07-29T19:00:08Z · sase-av.7] Implemented launcher-materialized artifact catalogs, core kind/payload completion and known-kind diagnostics, per-request LSP project selection, local-only bounded payload enumeration, tests, and editor documentation. Verified cargo fmt --all -- --check, cargo test --workspace, cargo clippy --workspace --all-targets -- -D warnings, focused Python tests (32 passed), just rust-lsp-install, sase lsp --version, bounded completion/diagnostic stdio smoke, and mandatory just check (23,753 passed, 7 skipped).

[2026-07-29T19:01:32Z · sase-av.7] Verified artifact-reference catalog generation, context-aware completion and diagnostics, project resolution, focused Python/Rust tests, full Rust workspace tests and clippy, live stdio LSP smoke, and a successful just check (23,753 passed, 7 skipped).

## Dependencies

- **Depends on:** [sase-av.1](sase-av.1.md) ✓
- **Depends on:** [sase-av.2](sase-av.2.md) ✓
- **Blocks:** [sase-av.8](sase-av.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-av.7--code | [sase-av.7](sase-av.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`334b987`](https://github.com/sase-org/sase-core/commit/334b987ae09afc5960ae9f4728c9803088839f60) | feat(editor): complete artifact references in xprompt LSP | [sase-av.7](sase-av.7.md) | 2026-07-29 19:02:38 |
