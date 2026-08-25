# Bead: sase-tt.5 — Cut the Python-side corpus marshalling cost

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.5` · **Size:** medium
**Created:** 2026-08-25 14:59:15 EDT · **Closed:** 2026-08-25 16:54:07 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

entry-projection: stop materializing each query row three times on the Python side and shrink the per-row projection work in the agent catalog's query-entry adapter, without changing the row wire shape.

## Notes

[2026-08-25T20:09:58Z · 0ds] INTEGRATION: the "byte-identical wire shape" invariant in this phase's plan section is
scoped to composing with sase-tt.4 in either order. It is not a permanent schema freeze.
Phase sase-tw.13 of epic sase-tw adds three fields — relation, artifact, and linked — to
the same agent-catalog wire dict. Write the golden test so that is a deliberate
one-line regeneration with a visible diff, and say so in the test's docstring, so the
next agent reads it as a change-detector rather than a wall.

Two things that make sase-tw.13 cheap if you leave room for them:

- agent_catalog_query_entry's signature is (row, *, project_ref_display=None).
  sase-tw.13 threads a link-facet map through as a second optional keyword-only
  argument. Keep the function keyword-extensible, and keep sase.agents.catalog
  Textual-free.
- The three new fields introduce no new wire types: linked is a bool like the existing
  hidden / dismissed / revivable / attention, and relation / artifact are multi-valued
  like the existing label / text / project. sase-tt.4's direct PyDict-to-QueryRow path
  therefore composes with them; only the golden collides.

sase-tw.13 adds per-row work to this exact function, which costs a measured 408ms over
11,783 rows today. It has been told on its own bead to re-run
tests/perf/bench_artifacts_first_paint.py and hold this epic's ≤400ms Agent target.

[2026-08-25T20:54:07Z · sase-tt.5] Implemented paired row/wire corpus marshalling and optimized agent catalog projection; verified .venv focused pytest, completion snapshot pytest, just _lint-symvision, and just check (passed).

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.5/README.md) | [sase-tt.5](sase-tt.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e394b9d`](https://github.com/sase-org/sase/commit/e394b9d9c062ee9b4e226442b201b0c598042890) | perf(query): reduce artifact row marshalling | [sase-tt.5](sase-tt.5.md) | 2026-08-25 16:55:27 EDT |
