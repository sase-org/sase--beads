# Bead: sase-b3.1 — Canonical fuzzy matcher in sase-core

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.1` · **Size:** medium
**Created:** 2026-07-30 08:18:16 UTC · **Closed:** 2026-07-30 08:27:53 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

fuzzy: add the shared tier/score/runs fuzzy matcher and its ordering comparator to crates/sase_core/src/editor/fuzzy.rs, with the three-pass alignment that makes highlights land on the segment the user meant.

## Notes

[2026-07-30T08:29:14Z · sase-b3.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace; published sase-core commit 36f1d29.

## Dependencies

- **Blocks:** [sase-b3.3](sase-b3.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b3.1/README.md) | [sase-b3.1](sase-b3.1.md) | 0 |
