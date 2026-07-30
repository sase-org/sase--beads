# Bead: sase-b3.2 — Bundled document discovery depth

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.2` · **Size:** small
**Created:** 2026-07-30 08:18:20 UTC · **Closed:** 2026-07-30 08:26:44 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

docwalk: teach plan/read.rs to discover markdown inside bundle directories one level below a month shard, skipping dot-directories and the prompts/specs trees the prompt corpus owns.

## Notes

[2026-07-30T08:26:44Z · sase-b3.2] Implemented document corpus bundle-depth discovery in linked sase-core and verified with cargo test -p sase_core explicit_document_corpora, cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-b3.6](sase-b3.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b3.2/README.md) | [sase-b3.2](sase-b3.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@1c7057f`](https://github.com/sase-org/sase-core/commit/1c7057fbd97519a4486ddeb9e07bd4d467090895) | fix(plan): discover bundled document corpora | [sase-b3.2](sase-b3.2.md) | 2026-07-30 08:29:59 |
