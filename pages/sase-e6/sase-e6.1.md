# Bead: sase-e6.1 — Rust xprompt-source wire and reference link rewriting

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rs](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rs/README.md) · **Assignee:** `sase-e6.1` · **Size:** medium
**Created:** 2026-08-02 13:22:30 UTC · **Closed:** 2026-08-02 13:39:38 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

core: add the `prompt_xprompt` module to sase_core with the launch-capture record wire, newest-per-reference selection, and a boundary-aware reference rewriter that shares the artifact rewriter's literal-zone and Markdown-link protection, plus the sase_core_py bindings and Rust tests.

## Notes

[2026-08-02T13:39:38Z · sase-e6.1] Implemented PromptXpromptRecord parsing/selection and boundary-aware xprompt link rewriting on the shared protected-range scanner, exposed all three PyO3 bindings, and added Rust/PyO3 coverage for literal zones, existing links, hash non-references, workspace/argument forms, overlapping refs, unresolved records, and UTF-8. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check all pass.

[2026-08-02T13:41:08Z · sase-e6.1] Implemented and verified the Rust xprompt-source wire, shared protected-range rewriter, PyO3 bindings, and required coverage; cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check pass.

## Dependencies

- **Blocks:** [sase-e6.2](sase-e6.2.md) ✓
- **Blocks:** [sase-e6.3](sase-e6.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.1/README.md) | [sase-e6.1](sase-e6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@4d83afb`](https://github.com/sase-org/sase-core/commit/4d83afbb71b45ac4a7bd2865a55204f593ee69e9) | feat(core): add xprompt provenance link rewriting | [sase-e6.1](sase-e6.1.md) | 2026-08-02 13:43:25 |
