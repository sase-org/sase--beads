# Bead: sase-tt.3 — Two-stage Agent pane load

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.3` · **Size:** medium
**Created:** 2026-08-25 14:59:13 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

agent-paint: paint the Agent pane from a bounded head slice and move the full-corpus query-index build into a background extension worker, using the shipped Files-pane two-stage pattern.

## Notes

[2026-08-25T20:09:20Z · 0ds] INTEGRATION: three constraints this phase's plan section does not state.

1. Do not start before sase-tj.10.3 lands on master. That phase ("Put the Agent pane in
   the fast-startup inventory and rebaseline the goldens") is IN_PROGRESS, rebaselines
   every artifacts_* PNG golden, and adds six new Agent-pane snapshots. An "index still
   building" affordance from this phase would need golden updates on top of that work.
   sase-tw.13 already carries this gate; this phase needs it too and does not have it.
   Check sase bead show sase-tj.10.3 first and wait rather than rebasing around it.

2. Give artifact_links a defined answer on the bounded pass. AgentsSnapshot already
   carries artifact_links: ArtifactLinksSnapshot, and load_agents_snapshot already calls
   load_artifact_links_snapshot(project) (agents_data.py:24-56). Decide explicitly
   whether the bounded head-slice load populates it or leaves it empty until the
   extension pass, and record which in the code. The aggregate is project-scoped, not
   row-scoped, so slicing rows does not shrink it, and epic sase-tw grows it from ~112
   to ~1,600+ rows.

3. State the semantics a filter term sees mid-extension, because phase sase-tw.13 of
   epic sase-tw will build three new filter fields (relation:, linked:, artifact:) on
   top of them. _filtered_agents_snapshot (agents_query.py:439-460) short-circuits only
   on a blank remainder, so any filter term with _query_index None returns pending —
   this phase's intended grow trigger, and correct. The seam to close is the other
   order: it computes matched_rows by intersecting result.matched_row_ids with
   snapshot.rows, so a full-corpus index over a still-bounded snapshot yields a silently
   short match_count. Either make it impossible to present a full index against a
   partial snapshot, or make the count explicitly a lower bound — _sync_agent_query_bar
   already accepts lower_bound and coverage_label for exactly that case.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.3/README.md) | [sase-tt.3](sase-tt.3.md) | 0 |
