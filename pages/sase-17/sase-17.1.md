# Bead: sase-17.1 — Phase 2A: Query Contract, Corpus, and Baseline Measurement

[Bead Pages](../README.md) / [sase-17](README.md) / sase-17.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-17.1`
**Created:** 2026-04-29 06:53:06 UTC · **Closed:** 2026-04-29 07:06:03 UTC
**Plan:** [202604/rust\_backend\_phase2\_query.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase2_query.md)

## Description

Make Python query behavior explicit so a Rust port can be checked. Add QueryTokenWire/QueryExprWire/QueryProgramWire/QueryErrorWire to the wire module, conversion helpers, a golden corpus covering tokens/AST/evaluation/error messages, and a benchmark harness for parse-only and parse+evaluate at 100/1k/10k specs. Inventory regex semantics (substring, not user-supplied regex).

## Notes

COMMIT: d2e55b59

## Dependencies

- **Blocks:** [sase-17.2](sase-17.2.md) ✓
- **Blocks:** [sase-17.3](sase-17.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ce7b508`](https://github.com/sase-org/sase/commit/ce7b508da02942c762c758648df4716a1c76f6e6) | chore(core): Phase 2A — query wire contract, golden corpus, and benchmark (sase-17.1) | [sase-17.1](sase-17.1.md) | 2026-04-29 07:05:47 |
| [`74195a7`](https://github.com/sase-org/sase/commit/74195a709a0634c7ea6d6c860173c2103bc522a1) | chore: close Phase 2A bead (sase-17.1) | [sase-17.1](sase-17.1.md) | 2026-04-29 07:06:28 |
