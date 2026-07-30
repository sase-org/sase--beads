# Bead: sase-b2.1 — Bead and agent reference grammar in sase-core

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.1` · **Size:** small
**Created:** 2026-07-30 01:33:11 UTC · **Closed:** 2026-07-30 01:46:52 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

core_grammar: add the `Bead { id }` and `Agent { name }` kind/payload wire variants with lexical-only validation, reject fragments on both, bump the artifact-reference wire schema to 2, and make one shared builtin-kind constant the single source of truth.

## Notes

[2026-07-30T01:46:52Z · sase-b2.1] core_grammar landed in the sase-core linked checkout (uncommitted): Bead{id}/Agent{name} kind+payload wire variants with lexical-only validation (validate_bead_id; validate_agent_reference_name wrapping the historical semantic-name rules, newly exported from agent_identity), fragments rejected on both via a shared kind_rejects_fragments guard in parse and render, both artifact-ref wire schema constants bumped to 2, and BUILTIN_ARTIFACT_REF_KINDS in editor/at_reference.rs is now the single Rust source of truth (diagnostics.rs's hardcoded list deleted) with bead/agent appended after file. Tests: round-trip cases for bead:sase-9z, bead:sase-9z.1, bead:sase-ag.land, agent:bbugyi200.athena.9w, agent:...--code; rejection cases for empty/dotted/slashed/spaced bead ids, agent:, agent:a/b, agent:.9w, and #L1 fragments on both; a schema_version==2 assertion. Updated the three stale schema-1 assertions in sase_core_py and the @-menu ordering/index assertions in the LSP grouped-completion test. Verified: cargo fmt --all --check clean, cargo clippy --workspace --all-targets --all-features clean, cargo test --workspace green (1045 sase_core lib tests + all crates).

## Dependencies

- **Blocks:** [sase-b2.2](sase-b2.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b2.1/README.md) | [sase-b2.1](sase-b2.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@c1ae5f5`](https://github.com/sase-org/sase-core/commit/c1ae5f55f85b93658588eb90a700d5fa5c5054cb) | feat(artifact-ref): add bead and agent reference grammar | [sase-b2.1](sase-b2.1.md) | 2026-07-30 01:48:13 |
