# Bead: sase-as.7 — Rust core document corpora for plan discovery

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.7` · **Size:** medium
**Created:** 2026-07-29 14:31:23 UTC · **Closed:** 2026-07-29 14:52:07 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

core-corpora: teach the Rust plan reader to scan caller-supplied `(root, kind)` document corpora instead of only its hardcoded `plans`/`research` sub-directory pair, and expose that through `search_plans` and the PyO3 `plan_search` binding without changing default behavior.

## Notes

[2026-07-29T14:52:07Z · sase-as.7] Implemented caller-supplied document corpora in Rust plan discovery/search and the optional PyO3 plan_search document_corpora binding while preserving omitted-parameter behavior. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace (all green); parent just install and committed-plan validation passed, all parent format/lint stages passed, and 23,560 parent tests passed with 7 skipped. Parent just check remains blocked only by unrelated generated-skill/plan-link validation drift and 5 unrelated ACE Axe PNG golden mismatches.

## Dependencies

- **Blocks:** [sase-as.8](sase-as.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-as.7 | [sase-as.7](sase-as.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`13cb8b7`](https://github.com/sase-org/sase-core/commit/13cb8b72e5bdae6ad3ebb7af0cee597cc79f4cd2) | feat(plan): support explicit document corpora | [sase-as.7](sase-as.7.md) | 2026-07-29 14:53:39 |
