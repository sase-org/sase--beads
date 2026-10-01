# Bead: sase-1dr.4.1 — Memory history semantics, cache, and query bindings in sase-core

[Bead Pages](../README.md) / [sase-1dr.4](sase-1dr.4.md) / sase-1dr.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) · **Assignee:** `sase-1dr.4.1.land`
**Created:** 2026-09-30 20:38:47 EDT · **Closed:** 2026-09-30 23:58:52 EDT
**Plan:** [202609/memory\_history\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/memory_history_core.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md

<!-- sase:links:end -->

## Description

sase-core can answer, from git alone, what each memory note, web, strand, instruction file, and asset was at any committed revision: its subject identity across renames, whether a provider shim aliased or diverged, what kind of change it was, who committed it, and which memory or config edits landed in the same instruction render. A disposable per-scope snapshot makes that answer incremental, and GIL-releasing query bindings expose it to Python without Python reimplementing lineage, classification, or diffing.

## Notes

[2026-10-01T03:58:52Z · sase-1dr.4.1.land] LAND VERIFICATION. All four phases are closed done. Read every child note. No epic notes of its own. epic-symbols sase-1dr.4.1 is empty.

Verified in sase-core at 11f29c3, not from the notes alone. Commits 26ffc55 (sase-1dr.4.1.1 subjects), 1c49a65 (.2 classify), f15f538 (.3 causes-feed), and 11f29c3 (.4 cache-queries) are the epic. memory_history is a facade module (mod.rs is mod/pub use plus a //! summary) registered in lib.rs between markdown_link_refs and migration, with no root pub use. sase_core_py registers all eight memory_history_ bindings and releases the GIL via allow_threads. Subject ids, shim aliasing, the priority-list classes, summaries, provenance, cause attribution (config and renderer via one batched diff-tree), changeset folding, and the merged feed match the plan's fixture contract. The snapshot key omits repo_root and cache_dir, sync reports fresh/folded/rebuilt, unclassified rows are not persisted, and upstream_ahead never fetches. Re-ran just test -p sase_core memory_history (36 passed) and just test -p sase_core_py memory_history (2 passed) on this tree.

Integration. Since 26ffc55, non-epic sase-core commits are cd26011 (prompt_prediction current-word completion) and 6121711 (tool-run demand/stats). Neither touches memory_history, file_history, or prose_diff, and neither should call the new queries. In the sase repo, commits since the epic started are capture (sase-1dr.1, sibling tracking evidence), agents unread-ack, an ace input-bar split, ace-tui next-word, and tool stats. The Python history service is sase-1dr.5, still blocked on this phase, so no caller was added here.

Follow-ups. All four phases proposed the same clean-base sase-core clippy -D warnings failure (clippy 1.95: nonminimal_bool, collapsible_if/match, manual_range_contains in agent_runtime, agent_scan, finalizer, fleet_owner_facts, provider_usage, tool_run). Not caused by this epic: memory_history is clippy-clean and agent_runtime.rs:567 still has the pre-existing range form at HEAD 11f29c3. Corroborated ready task sase-1an (+8). No new task. Declined a separate instruction content-rename tale: step 10 already classifies a word-changing rename as authored, the corpus asserts that, and the fixture never content-renames an instruction file.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.land/README.md) | [sase-1dr.4.1](sase-1dr.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@7d55fe6`](https://github.com/sase-org/sase--plans/commit/7d55fe66d5b58923ddbcb3fb169c48bf2f8a3072) | docs(plan): mark the memory history core epic done | [sase-1dr.4.1](sase-1dr.4.1.md) | 2026-10-01 00:29:43 EDT |
