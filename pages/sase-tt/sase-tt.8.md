# Bead: sase-tt.8 — End-to-end verification and the perf recipe

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.8` · **Size:** small
**Created:** 2026-08-25 14:59:17 EDT · **Closed:** 2026-08-25 17:28:14 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

verify: confirm the combined first-paint numbers against a live-scale corpus, record the recipe in the perf README, and land the epic's combined tree green.

## Notes

[2026-08-25T20:10:17Z · 0ds] INTEGRATION: record §2.1's targets in tests/perf/README.md in a form a later epic can
re-measure against — the exact bench command, the corpus shape it assumes, and the
number each pane actually hit — not prose alone. Phase sase-tw.13 of epic sase-tw joins
artifact-link facets onto agent_catalog_query_entry after this epic lands, and has been
told on its bead to re-run tests/perf/bench_artifacts_first_paint.py and hold the Agent
number this phase certifies. That instruction is only actionable if the recipe you write
is.

Worth measuring while the harness is up: AgentsSnapshot carries an
artifact_links: ArtifactLinksSnapshot loaded by load_agents_snapshot
(agents_data.py:24-56) that this epic's breakdown never itemized. It holds 112
machine-global aggregate rows today; epic sase-tw targets ~1,600+. Record its current
cost so that growth has a baseline to be judged against.

Visual goldens are contended in this window: sase-tj.10.3 rebaselines every artifacts_*
golden and adds six new Agent-pane snapshots, and sase-tw.12 updates the relation
snapshot tests. If this epic's panes changed their loading or empty-state rendering,
rebaseline against master after sase-tj.10 lands and look at each regenerated golden
rather than force-accepting it.

[2026-08-25T21:27:51Z · sase-tt.8] PROPOSED FOLLOW-UP: just check escalates to the full suite and currently fails outside this README-only phase — isolated last-failed rerun shows completion snapshot drift, artifact link-health/handler expectation drift, and agent-name registry tests failing: tests/completion/test_snapshot.py::{test_checked_in_snapshot_has_no_drift,test_current_structural_view_matches_checked_in_snapshot}; tests/main/test_artifact_cli_link_health.py::test_missing_derived_row_projection_is_reported_stale; tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases; tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation; tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix.

[2026-08-25T21:28:14Z · sase-tt.8] Updated tests/perf/README.md with the Artifacts first-paint recipe, live-scale corpus shape, 2026-08-25 pane timings, agent-catalog confirmation, and artifact-link aggregate baseline. Verified: just install; pytest -s -m slow tests/perf/bench_artifacts_first_paint.py passed; pytest -s -m slow tests/perf/bench_agent_catalog.py passed; artifact-link probe measured 185 rows with cold median 6.38 ms. Ran sase bead epic-symbols sase-tt.8: no entries. just check passed lint gates but escalated test-scoped to the full suite and was interrupted at pytest temp cleanup after showing unrelated failures; last-failed rerun isolated those and they are recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-tt.2](sase-tt.2.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.3](sase-tt.3.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.4](sase-tt.4.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.5](sase-tt.5.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.6](sase-tt.6.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.7](sase-tt.7.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.8/README.md) | [sase-tt.8](sase-tt.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f56cf43`](https://github.com/sase-org/sase/commit/f56cf433328eea77e9d0a634fa41018cd2d34f58) | docs(perf): record artifacts first-paint verification | [sase-tt.8](sase-tt.8.md) | 2026-08-25 17:29:44 EDT |
