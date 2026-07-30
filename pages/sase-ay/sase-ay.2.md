# Bead: sase-ay.2 — PyO3 bindings for the reference menu

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.2` · **Size:** small
**Created:** 2026-07-29 22:24:00 UTC · **Closed:** 2026-07-29 23:08:07 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

binding: export `at_reference_context` and `at_reference_menu` from `sase_core_py` as JSON-dict functions in the style of `placeholder_completion`, with binding-level tests.

## Notes

[2026-07-29T23:08:07Z · sase-ay.2] Implemented PyO3 at_reference_context and at_reference_menu bindings in sase-core, added binding JSON-shape coverage, bumped workspace crates to 0.12.15, verified with cargo test -p sase_core_py at_reference_bindings_return_plain_json_shapes and just rust-check.

## Dependencies

- **Depends on:** [sase-ay.1](sase-ay.1.md) ✓
- **Blocks:** [sase-ay.6](sase-ay.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ay.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ay.2/README.md) | [sase-ay.2](sase-ay.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@dba90da`](https://github.com/sase-org/sase-core/commit/dba90da3b781bc5cd4c59a82d5fc47ceb24f33a2) | feat(py): expose at-reference menu bindings | [sase-ay.2](sase-ay.2.md) | 2026-07-29 23:14:29 |
