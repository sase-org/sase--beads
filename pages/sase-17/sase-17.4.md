# Bead: sase-17.4 — Phase 2D: PyO3 Binding and Python Facade Integration

[Bead Pages](../README.md) / [sase-17](README.md) / sase-17.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-17.4`
**Created:** 2026-04-29 06:53:38 UTC · **Closed:** 2026-04-29 07:41:42 UTC
**Plan:** [202604/rust\_backend\_phase2\_query.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase2_query.md)

## Description

Expose the Rust query engine via sase_core_rs and route Python query calls through it only when requested. Add PyO3 functions tokenize_query/parse_query/canonicalize_query/evaluate_query_many. Convert QueryErrorWire into ValueError or specific Python exception. In sase_101: add ChangeSpec->ChangeSpecWire adapters reusing changespec_to_wire/to_json_dict, register Rust impls in query_facade, preserve parse_query/evaluate_query/evaluate_query_with_context signatures, add batch facade evaluate_query_many (and optional compile_query/evaluate_compiled_query_many), and SASE_CORE_DUAL_RUN=1 comparison.

## Notes

COMMIT: a29d98a2

## Dependencies

- **Depends on:** [sase-17.2](sase-17.2.md) ✓
- **Depends on:** [sase-17.3](sase-17.3.md) ✓
- **Blocks:** [sase-17.5](sase-17.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7d23ac5`](https://github.com/sase-org/sase/commit/7d23ac5de9b0b8763ff7d1d12e5270980c93ff1f) | feat(core): Phase 2D — wire Rust query bindings into facade (sase-17.4) | [sase-17.4](sase-17.4.md) | 2026-04-29 07:41:46 |
