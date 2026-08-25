# Bead: sase-tw.13 — \`relation:\`, \`linked:\`, and \`artifact:\` on the Agent pane

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.13` · **Size:** medium
**Created:** 2026-08-25 15:34:44 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

agent-pane-filters: join artifact-link facets onto the agent catalog query entry and declare the three link fields in the agents profile so both the Artifacts Agent pane and `sase agent search` can filter on them.

## Notes

[2026-08-25T20:11:46Z · 0ds] INTEGRATION: this phase's "Do not start until sase-tj.10 has landed" gate is necessary
but not sufficient. A second in-flight epic, sase-tt ("Make Artifacts sub-tab queries
fast, starting with the Agent pane", plan:202608/artifacts_query_performance.md),
rewrites all four files this phase lists. Wait for epic sase-tt to land on master as
well, and re-read src/sase/ace/tui/widgets/artifacts/agents_data.py and
src/sase/agents/catalog/_query.py before starting — both will have changed shape.

Three consequences.

1. The wire golden. sase-tt.5 lands a test asserting the agent-catalog wire dict is
   byte-identical for a fixed corpus. Adding relation, artifact, and linked changes it.
   That regeneration is expected and deliberate: look at the diff, do not force-accept
   it. No new wire types are introduced — linked is a bool like the existing hidden /
   dismissed, and relation / artifact are multi-valued like the existing label / text /
   project — so sase-tt.4's direct PyDict-to-QueryRow path composes with them.

2. Hold the perf budget. sase-tt.5 shrinks agent_catalog_query_entry, which costs a
   measured 408ms over 11,783 rows today, and sase-tt.8 certifies an Agent-pane
   first-paint target of ≤400ms into tests/perf/README.md. The facet join this phase
   adds is per-row work on that exact function. Build the facet map once per load and
   index it by agent name rather than scanning rows per lookup; run
   tests/perf/bench_artifacts_first_paint.py before and after and report both numbers on
   this bead. If the target cannot be held, say so here rather than quietly moving it.
   AgentsSnapshot already carries the ArtifactLinksSnapshot (agents_data.py:24-56), so
   no new load is needed — but after sase-tt.3 the pane paints from a bounded head
   slice, so check whether the bounded pass populates that field before depending on it.

3. Assert the acceptance counts on a complete snapshot. The stated acceptance —
   "linked:false returns agents with no rows and its count plus linked:true's equals the
   unfiltered total" — is a whole-corpus invariant. After sase-tt.3 the pane paints from
   a bounded head slice with AgentsSnapshot.complete False and builds the full-corpus
   index in a background extension worker, and _filtered_agents_snapshot intersects
   result.matched_row_ids with the loaded snapshot.rows (agents_query.py:452-460).
   Assert that invariant only against complete=True. Otherwise this phase reproduces,
   from a different cause, exactly the "confidently wrong answers" failure it cites
   index-durability as the fix for: a lossy index is not the only way the corpus can be
   incomplete.

## Dependencies

- **Depends on:** [sase-tw.1](sase-tw.1.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.12](sase-tw.12.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.14](sase-tw.14.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.13/README.md) | [sase-tw.13](sase-tw.13.md) | 0 |
