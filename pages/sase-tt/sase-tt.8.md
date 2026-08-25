# Bead: sase-tt.8 — End-to-end verification and the perf recipe

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.8` · **Size:** small
**Created:** 2026-08-25 14:59:17 EDT
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

## Dependencies

- **Depends on:** [sase-tt.2](sase-tt.2.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.3](sase-tt.3.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.4](sase-tt.4.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.5](sase-tt.5.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.6](sase-tt.6.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tt.7](sase-tt.7.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.8/README.md) | [sase-tt.8](sase-tt.8.md) | 0 |
