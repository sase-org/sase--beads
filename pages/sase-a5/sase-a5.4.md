# Bead: sase-a5.4 — Cache the annotated hint document

[Bead Pages](../README.md) / [sase-a5](README.md) / sase-a5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a5.4` · **Size:** medium
**Created:** 2026-07-27 18:21:56 UTC · **Closed:** 2026-07-27 20:38:25 UTC
**Plan:** [202607/agents\_view\_hints\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_view_hints_perf.md)

## Description

cache: memoize the hint render result and wrap the annotated document in a width-keyed cached renderable so repeat presses, refresh repaints, and post-enrichment repaints reuse rendered segments.

## Notes

[2026-07-27T20:38:05Z · sase-a5.4] Implemented a bounded panel-local LRU for annotated hint documents, keyed by agent/header state, fold overrides, source-content digests, detail-summary identity, cap parameters, and attempt mode/pin. Cache hits reuse both AgentHintRender mappings and a width/options-cached Rich renderable; caches clear on agent identity changes and show_empty. Verification: 73 focused hint/family/header/lazy-render tests passed; Pilot view-hints benchmark passed with 8.41 ms cold vs 0.44 ms warm repeat (baseline repeat median 18.23 ms; ~97.6% lower) and 0 annotated chars on warm hits; full run reached 22,780 passed/7 skipped with two unrelated xdist/resource flakes that both passed in isolation. All fmt, ruff, mypy, pyscripts, Symvision, and toobig gates pass. Final just check is blocked only by pre-existing external init-skills drift in five generated sase_beads provider copies.

## Dependencies

- **Depends on:** [sase-a5.2](sase-a5.2.md) ✓
- **Blocks:** [sase-a5.5](sase-a5.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a5.4/README.md) | [sase-a5.4](sase-a5.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`57c5b8c`](https://github.com/sase-org/sase/commit/57c5b8c6a9007fae7c6b18ba4ea56b9e038be88a) | perf(tui): cache annotated hint documents (sase-a5.4) | [sase-a5.4](sase-a5.4.md) | 2026-07-27 20:41:17 |
