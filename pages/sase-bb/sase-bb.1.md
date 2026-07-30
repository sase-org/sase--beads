# Bead: sase-bb.1 — Shared reference-list codec and the ChangeSpec REFS section

[Bead Pages](../README.md) / [sase-bb](README.md) / sase-bb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bb.1` · **Size:** medium
**Created:** 2026-07-30 14:53:38 UTC · **Closed:** 2026-07-30 15:33:38 UTC
**Plan:** [202607/spec\_artifact\_references.md](https://github.com/sase-org/sase--plans/blob/main/202607/spec_artifact_references.md)

## Description

core-refs: add the Rust parse/normalize/render/batch-resolve API for stored artifact-reference lists, expose it through the PyO3 binding, and teach the Rust ChangeSpec parser the new REFS section behind a wire-schema bump.

## Notes

[2026-07-30T15:33:38Z · sase-bb.1] Implemented the shared Rust artifact-reference list parse/normalize/batch-resolve codec with one artifact-index load per batch and tolerant unknown_kind results, exposed all four PyO3 bindings, and added raw REFS parsing, schema 5, and searchable-text parity for ChangeSpecs. Verified cargo fmt --check, cargo test --workspace, and cargo clippy --workspace --all-targets -D warnings; 52 phase-owned Python tests pass. Full Python run reached 24,262 passes; its two phase snapshot failures were updated and now pass, leaving only three unrelated pre-existing artifact-file query handshake failures (Python expects wire 2, opened core master reports 3). Repository formatting, ruff, mypy, pyscript, and changelog checks pass; global just check is externally blocked by stale closed-bead Symvision metadata and unrelated plan-link validation errors.

## Dependencies

- **Blocks:** [sase-bb.2](sase-bb.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bb.1/README.md) | [sase-bb.1](sase-bb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@a25d174`](https://github.com/sase-org/sase-core/commit/a25d174abcb17e181a4145f4c793a5968f126313) | feat!: add artifact reference list APIs | [sase-bb.1](sase-bb.1.md) | 2026-07-30 15:35:52 |
