# Bead: sase-ho.1 — Add the shared reference and filter contract to sase-core

[Bead Pages](../README.md) / [sase-ho](README.md) / sase-ho.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vw/README.md) · **Assignee:** `sase-ho.1` · **Size:** large
**Created:** 2026-08-08 13:32:29 EDT · **Closed:** 2026-08-08 14:32:27 EDT
**Plan:** [202608/artifact\_reference\_xprompts.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_reference_xprompts.md)

## Description

core-ref-contract: extend the Rust content-layout, artifact-reference, catalog, and completion wires with contextual ref sources, path filters, and deterministic filtered-path behavior.

## Notes

[2026-08-08T18:32:27Z · sase-ho.1] Implemented the Rust core ref contract in linked sase-core: ref source layout/catalog metadata, artifact context schema/path_globs, shared POSIX path filtering, filtered resolution/canonicalization/inventory, PyO3 bindings, gateway contract, and LSP #ref/<kind> argument completion. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, plus targeted artifact_ref/xprompt_catalog/PyO3/LSP tests.

[2026-08-08T18:34:16Z · sase-ho.1] Verified linked sase-core changes with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-ho.2](sase-ho.2.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-ho.4](sase-ho.4.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ho.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ho.1.md) | [sase-ho.1](sase-ho.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4071bf0`](https://github.com/sase-org/sase-core/commit/4071bf083ea59e1ecdb97a64c816d272f3f5ad66) | feat(core)!: add reference artifact contract | [sase-ho.1](sase-ho.1.md) | 2026-08-08 14:36:01 EDT |
