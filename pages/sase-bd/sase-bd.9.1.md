# Bead: sase-bd.9.1 — Unblock sase-core master

[Bead Pages](../README.md) / [sase-bd.9](sase-bd.9.md) / sase-bd.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.9.1` · **Size:** small
**Created:** 2026-07-30 20:14:45 UTC · **Closed:** 2026-07-30 20:21:57 UTC
**Plan:** [202607/bead\_close\_integrity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity_landing.md)

## Description

core-clippy: fix the `clippy::question_mark` denial in the doctor reader that has kept sase-core master red since the projection-drift commit, sweep the neighbouring commits for the same class of denial, and confirm master CI goes green so release-plz can cut a release.

## Notes

[2026-07-30T20:32:31Z · sase-bd.9.1] Fixed the clippy::question_mark denial at crates/sase_core/src/bead/read.rs:232 by collapsing the match on read_legacy_jsonl_issues into the ? form. Swept the workspace rather than stopping at the first reported error, which surfaced a second denial hidden behind it (clippy stops at the first error per crate): a needless_borrow at crates/sase_core/tests/bead_read_parity.rs:594 passing &stream where stream was already a reference. Verified with the exact commands core CI runs: cargo fmt --all -- --check clean, cargo clippy --workspace --all-targets -- -D warnings clean, cargo test --workspace fully green (all suites, 0 failures; PYO3_PYTHON and LD_LIBRARY_PATH pointed at a 3.12 interpreter for the local pyo3 build). Committed and pushed to sase-core master as 407965e 'fix(bead): satisfy clippy in the doctor reader'. Master CI run 30578914929 for that commit concluded success with both jobs green: 'cargo fmt + clippy + test' and 'maturin build + import smoke'. Core master is no longer red, so release-plz can cut a release; PR #63 'chore: release v0.15.0' remains open for the core-release phase.

## Dependencies

- **Blocks:** [sase-bd.9.2](sase-bd.9.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.9.1/README.md) | [sase-bd.9.1](sase-bd.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@407965e`](https://github.com/sase-org/sase-core/commit/407965ef793c629511d972e3c30f9a767a1cd898) | fix(bead): satisfy clippy in the doctor reader | [sase-bd.9.1](sase-bd.9.1.md) | 2026-07-30 20:22:53 |
