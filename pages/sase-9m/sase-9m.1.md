# Bead: sase-9m.1 — Placeholder candidate sources and common-tag input in sase-core

[Bead Pages](../README.md) / [sase-9m](README.md) / sase-9m.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9m.1` · **Size:** medium
**Created:** 2026-07-25 16:44:21 UTC
**Plan:** [202607/common\_placeholder\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202607/common_placeholder_tags.md)

## Description

'Phase core — sase-core: candidate sources and common-tag input' section: extend the Rust placeholder completion engine so candidates carry a prompt/common source, accept a caller-supplied common-tag list, and emit prompt-local candidates before common ones; update the PyO3 binding, the xprompt LSP call sites, and the version contract.

## Notes

Implemented in the linked sase-core checkout + this repo.

sase-core:
- crates/sase_core/src/editor/placeholder.rs: added PlaceholderCandidateSource {Prompt,Common} and PlaceholderCandidate {text, source}; PlaceholderCompletion.candidates is now Vec<PlaceholderCandidate>; build_placeholder_completion_candidates gained a trailing common: &[String] param that appends caller-order common entries after the document-order pass, sharing the same case-insensitive prefix filter and 'seen' dedup set; into_completion_list emits detail 'placeholder' vs 'saved placeholder' while kind stays 'placeholder'. New unit tests cover caller-order append, cross-group and intra-group dedup, prefix filtering of common entries, empty-slice parity, per-source detail, and the {text, source} serde shape.
- crates/sase_core/src/editor/mod.rs + src/lib.rs: re-export the two new types.
- crates/sase_xprompt_lsp/src/server.rs: single call site passes &[]; lsp_convert.rs::placeholder_completion_response consumes CompletionList and needed no change, so LSP output is unchanged and its existing tests are the proof.
- crates/sase_core_py/src/lib.rs: placeholder_completion(text, line, character, common=None) via #[pyo3(signature = ...)]; module docstring updated; placeholder_bindings_return_plain_json_shapes extended for the dict shape and the common argument.

sase:
- src/sase/xprompt/placeholder_completion.py: _completion_from_dict reads candidate['text'] so the existing tuple[str, ...] surface and all TUI callers keep working. Phase 'wiring' replaces this with the PlaceholderCandidate dataclass.
- tests/test_xprompt_placeholder_completion.py: fake binding payload uses the new candidate shape.

DEVIATION FROM THE PLAN - version contract not applied.
The plan asked to bump the sase-core workspace version 0.9.1 -> 0.9.2 and raise the pyproject floor to sase-core-rs>=0.9.2,<0.10.0. Both were reverted for two blocking reasons:
1. sase-core/AGENTS.md: release-plz owns [workspace.package].version; manual version edits during feature work are forbidden and require explicit user approval plus a 'manual-version' PR label.
2. sase-core-rs 0.9.2 is not published (PyPI returns 404), so tools/validate_sase_core_rs_version's published-minimum check would fail on a raised floor.
Instead, land the sase-core change under a Conventional Commit so release-plz computes the version. Note the public API break (build_placeholder_completion_candidates signature and PlaceholderCompletion.candidates type) argues for 'feat!:' / a BREAKING CHANGE footer, which on 0.x yields 0.10.0 rather than 0.9.2 and would also need the pyproject upper bound revisited. Raise the sase floor only after the core release is published.

Verification: cargo fmt --check clean, cargo clippy --workspace --all-targets -D warnings clean, cargo test --workspace all 24 binaries ok. just install + just check here: lint/mypy/fmt clean; the full suite reported 5 failures (1 diff-cache, 4 PNG snapshots) that all pass on re-run in isolation - flakes from four other workspaces running their suites concurrently, none touching placeholder completion. Placeholder suites (tests/test_xprompt_placeholder_completion.py, tests/ace/tui/widgets/test_placeholder_completion.py, the placeholder PNG snapshots) all pass.

Also formatted tests/ace/tui/widgets/test_agent_list_status_indicators.py, which was left ruff-unformatted by HEAD commit 899a257f2 and was blocking 'just check' before reaching any test.

## Dependencies

- **Blocks:** [sase-9m.3](sase-9m.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9m.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9m.1/README.md) | [sase-9m.1](sase-9m.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`26b4a4c`](https://github.com/sase-org/sase/commit/26b4a4cc936d3270f654c6ab20fe7b5e1ec75f36) | fix(xprompt): read the new placeholder candidate shape from sase-core (sase-9m.1) | [sase-9m.1](sase-9m.1.md) | 2026-07-25 17:11:51 |
