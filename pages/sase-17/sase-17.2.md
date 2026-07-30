# Bead: sase-17.2 — Phase 2B: Pure-Rust Query Tokenizer and Parser

[Bead Pages](../README.md) / [sase-17](README.md) / sase-17.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-17.2`
**Created:** 2026-04-29 06:53:13 UTC · **Closed:** 2026-04-29 07:17:19 UTC
**Plan:** [202604/rust\_backend\_phase2\_query.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase2_query.md)

## Description

Implement the Python query grammar in ../sase-core's pure crate without touching Python dispatch. Add crates/sase_core/src/query/{tokenizer,parser,types,mod}.rs mirroring Python token quirks (! @ $ standalone, !! !@ !$, *, %y => READY, property values), parser precedence (NOT tightest, implicit AND, OR loosest, * expands to Or(!!!,@@@,$$$)), Rust unit tests from the 2A corpus, and pure exports tokenize_query/parse_query/canonicalize_query. No PyO3 in the pure crate.

## Notes

COMMIT: 099a96ff

## Dependencies

- **Depends on:** [sase-17.1](sase-17.1.md) ✓
- **Blocks:** [sase-17.3](sase-17.3.md) ✓
- **Blocks:** [sase-17.4](sase-17.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@849dd9e`](https://github.com/sase-org/sase-core/commit/849dd9e3f51fd0f2fa2982b43febb7d0674ad377) | feat(query): Phase 2B pure-Rust query tokenizer and parser (sase-17.2) | [sase-17.2](sase-17.2.md) | 2026-04-29 07:15:12 |
| [`91e433a`](https://github.com/sase-org/sase/commit/91e433a9ea90bc2a2d4b0e3e863459aa8fef48ff) | chore: close sase-17.2 (Phase 2B done in sase-core) (sase-17.2) | [sase-17.2](sase-17.2.md) | 2026-04-29 07:17:24 |
