# Bead: sase-av.1 — Kind-tagged artifact reference grammar in the Rust core

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.1` · **Size:** large
**Created:** 2026-07-29 16:45:28 UTC · **Closed:** 2026-07-29 17:13:28 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

ref-core: add the `artifact_ref` module to the Rust core — parse, render, canonicalize, and resolve kind-tagged references with per-kind payloads, fragment anchors, caller-supplied document roles, and a prompt-text scanner — reusing the `plans:` machinery without changing any `plan/refs.rs` behavior, and expose it through new PyO3 bindings.

## Notes

[2026-07-29T17:13:28Z · sase-av.1] Implemented the pure-Rust artifact_ref grammar, typed serde wire/context records, canonicalization and local resolution for document/chat/file/commit/bug references, prompt scanner byte spans, compatibility-preserving shared plan-reference helpers, and all six PyO3 bindings. Verified cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace; targeted artifact_ref, plan::refs, and PyO3 binding tests; git diff --check. Release versions and dependency pins were unchanged.

[2026-07-29T17:14:30Z · sase-av.1] Verified cargo fmt --check, cargo clippy --workspace --all-targets --all-features -- -D warnings, full workspace tests, targeted artifact-reference/PyO3 tests, and git diff --check.

## Dependencies

- **Blocks:** [sase-av.2](sase-av.2.md) ✓
- **Blocks:** [sase-av.7](sase-av.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.1.md#member-code) | [sase-av.1](sase-av.1.md) | 1 |
| [bbugyi200.athena.sase-av.1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.1.md#member-plan) | [sase-av.1](sase-av.1.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@6c2adc4`](https://github.com/sase-org/sase-core/commit/6c2adc420a5ee24aecfe5fae305e2c869ab7b627) | feat: add core artifact reference APIs | [sase-av.1](sase-av.1.md) | 2026-07-29 17:15:02 |
