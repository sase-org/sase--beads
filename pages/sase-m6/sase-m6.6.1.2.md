# Bead: sase-m6.6.1.2 — Parameterize the Rust parser, corpus, and Python binding

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.2` · **Size:** large
**Created:** 2026-08-15 06:17:41 EDT · **Closed:** 2026-08-15 07:39:06 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

rust_engine: in sase-core, replace the hard-coded property allowlist and Patch-only QueryCorpus assumptions with the compiled profile and generic precomputed rows, parameterize tokenization, parsing, sigils, predicates, macros, searchable text and boolean mode, expose the profile-driven calls through the Python binding, preserve compatibility entry points, and extend Rust parser, corpus, and evaluator parity tests before updating the host adapter.

## Notes

[2026-08-15T11:39:06Z · sase-m6.6.1.2] Implemented the profile-driven Rust query engine in sase-core.

The parser, persistent corpus, evaluator, and sase_core_rs binding now consume CompiledQueryProfile.to_wire() plus generic precomputed rows. Existing tokenize_query/parse_query/canonicalize_query/compile_query/compile_corpus/evaluate_many/evaluate_query_many entry points remain Patch-compatible wrappers over the built-in Patch profile (digest matches the Python compiler: d93ceed27574ae2a09970b0ecd6dad4f5d63e34cd6dcb6475de471d23f2d81a4).

Verification:
- cargo test -p sase_core --lib query (136 passed, including new profile/flat/generic-row cases)
- cargo test -p sase_core --test query_evaluator_parity (17 passed, including explicit-profile golden matrix)
- cargo test -p sase_core_py profile_binding and query_ (legacy handles unchanged; generic profile dicts, invalid profiles, and digest mismatch covered)
- just check in sase-core (fmt, clippy -D warnings, full workspace tests) passed
- sase repo worktree unchanged; sase-core changes are limited to the query crate, PyO3 binding, changelogs, and PYPI_README

[2026-08-15T11:41:23Z · sase-m6.6.1.2] Profile-driven Rust query engine landed in sase-core. Parser, corpus, evaluator, and sase_core_rs consume CompiledQueryProfile.to_wire() plus generic precomputed rows; existing Patch APIs remain compatibility wrappers. Verified: query unit tests (profile/flat/generic-row cases), query_evaluator_parity (17 passed, golden matrix on both compatibility and explicit Patch-profile paths), PyO3 profile and legacy query handle tests, and sase-core just check (fmt, clippy -D warnings, full workspace tests). Parent epic left open.

## Dependencies

- **Depends on:** [sase-m6.6.1.1](sase-m6.6.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.1.2.md) | [sase-m6.6.1.2](sase-m6.6.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ba78216`](https://github.com/sase-org/sase-core/commit/ba7821682990377dae42ad9c8a08392592470f54) | feat(query): parameterize the Rust query engine by compiled profile | [sase-m6.6.1.2](sase-m6.6.1.2.md) | 2026-08-15 07:43:27 EDT |
