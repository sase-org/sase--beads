# Bead: sase-86.5 — Fixed recipe overhead trim

[Bead Pages](../README.md) / [sase-86](README.md) / sase-86.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-86.5` · **Size:** small
**Created:** 2026-07-20 15:00:04 UTC
**Plan:** [202607/fast\_test\_suite.md](https://github.com/sase-org/sase--plans/blob/main/202607/fast_test_suite.md)

## Description

'Fixed recipe overhead trim' section: measure and cut the ~30-50s of non-pytest overhead in every `just test` invocation (dependency-validation scripts, nested just recursion, collection) without touching tools/run_pytest.

## Notes

Added per-venv cached setup validation for core version/bindings, dependency groups, and editable metadata; fingerprints pyproject.toml, uv.lock, validator sources, core Cargo.toml, venv metadata, and the installed extension; replays diagnostics; serializes cache access; supports SASE_TEST_SETUP_FORCE_REVALIDATE=1. Updated Justfile setup recipes, development docs, and invalidation/force/custom-venv tests. Hot _setup-visual benchmark: 167 ms mean over 10 runs; prior direct validators totaled about 350 ms. Verification: focused tests green; just check green on rerun (first concurrent-load run had one unrelated statistics-pane soak failure that passed alone).

## Dependencies

- **Blocks:** [sase-86.6](sase-86.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-86.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-86.5/README.md) | [sase-86.5](sase-86.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4c46711`](https://github.com/sase-org/sase/commit/4c46711115fa8de5c9098798f3c9f1b26e862b61) | perf(test): cache setup environment validation (sase-86.5) | [sase-86.5](sase-86.5.md) | 2026-07-20 15:33:11 |
