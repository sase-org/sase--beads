# Bead: sase-b3.10.1 — Fuzzy ranking in the agent and indexed-file collectors

[Bead Pages](../README.md) / [sase-b3.10](sase-b3.10.md) / sase-b3.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.10.1` · **Size:** small
**Created:** 2026-07-30 10:57:03 UTC · **Closed:** 2026-07-30 11:09:28 UTC
**Plan:** [202607/editor\_artifact\_ref\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202607/editor_artifact_ref_parity.md)

## Description

rank: replace the case-insensitive starts_with prefilters in append_agent_page_candidates and append_artifact_index_candidates with the shared fuzzy matcher, ranking with compare_fuzzy and capping after ranking so prefix reach cannot regress.

## Notes

[2026-07-30T11:09:28Z · sase-b3.10.1] Replaced the case-insensitive starts_with prefilters in append_agent_page_candidates and append_artifact_index_candidates (crates/sase_core/src/editor/completion.rs) with the shared fuzzy_match, collecting every match, sorting via the new append_ranked_artifact_ref_candidates helper with compare_fuzzy, and capping to ARTIFACT_REF_MAX_RESULTS after ranking. Verified against the real sase agent sidecar (5466 published pages): before, every non-empty query returned 0 rows because agent payloads are global names (bbugyi200.athena.*); after, @agent:sase-b3 returns 19 rows. Cost per request 22-31ms, dominated by the directory walk (a non-matching prefix query already cost ~21ms pre-change); match+rank over 5466 candidates adds ~4-9ms, well inside budget, and the empty-query case rose 5.9ms -> 31ms because full enumeration replaces the early break at 200 pushed rows - the walk cache in phase reach (sase-b3.10.3) removes it, as the plan anticipated. New tests: agent_and_indexed_file_payloads_match_mid_name_fragments (@agent: mid-name fragment reaches a published page; @file:931185 digest fragment reaches its id) and agent_prefix_query_survives_a_corpus_of_fuzzy_matches (goal-4 gate: a tier-0 prefix row sorted last in walk order survives 205 fuzzy matches ahead of it). Existing prefix assertions in builds_agent_payload_candidates_from_published_pages and builds_chat_and_indexed_file_payloads_but_not_remote_kinds kept and passing. Gates in sase-core: cargo fmt --all --check clean, cargo clippy --workspace --all-targets -D warnings clean, cargo test --workspace all 24 binaries ok. No Python-visible binding changed (the symbol is only a Rust-internal re-export), so no sase-side change and no just check needed.

## Dependencies

- **Blocks:** [sase-b3.10.3](sase-b3.10.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b3.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b3.10.1/README.md) | [sase-b3.10.1](sase-b3.10.1.md) | 0 |
