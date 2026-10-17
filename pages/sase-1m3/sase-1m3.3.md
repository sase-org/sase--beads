# Bead: sase-1m3.3 — Statistics registry, neutral render primitives, palette, and range grammar

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.3` · **Size:** medium
**Created:** 2026-10-16 22:05:21 EDT · **Closed:** 2026-10-17 02:58:52 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

foundation: a zero-visual-diff refactor that promotes the view specs and legends into `sase.stats.registry`, moves the loader out of the TUI package, extracts Textual-free render primitives and the provider palette, and adds one shared range parser.

## Notes

[2026-10-17T02:54:00Z · sase-1m3.3] PROPOSED FOLLOW-UP: skipped decisions-web record — stats_decision_record=no; do not edit decisions. If the land agent still wants the record, file a memory task: stats count each fact at its durable source, and footers stamp only underivable facts.

[2026-10-17T06:58:14Z · sase-1m3.3] PROPOSED FOLLOW-UP: docs-gen-check CLI wrap drift from local sase_core_rs 0.40.1 vs pyproject sase-core-rs>=0.35.0,<0.36.0 — do not land docs/reference/cli/* from this workspace; CI uses 0.35.x

[2026-10-17T06:58:24Z · sase-1m3.3] PROPOSED FOLLOW-UP: docs-lint E5 on unrelated reference pages (reference/agents/initialization.md, memory-initialization.md, config/core-behavior.md, memory/memory.md, providers/agent-clis.md) — pre-existing, not Statistics

[2026-10-17T06:58:34Z · sase-1m3.3] PROPOSED FOLLOW-UP: just check full-suite NEW agent-session/raw-prompt/auto-restart failures after core-identity-changed (sase-core 0.40.1); possible owners sase-1ma, sase-1i9, sase-1l3, sase-1hy, sase-1ki — not this phase

[2026-10-17T06:58:52Z · sase-1m3.3] foundation: registry/loader/primitives/palette/parse_stats_range landed; TUI shims keep load_statistics_view; 74 terminology+foundation tests pass; targeted Statistics PNG 19/19 unchanged; just _lint-symvision clean after facade re-exports of MetricLegend/StatisticsGrouping/ProviderPalette; no --epic-symbol leftovers for this phase; skipped decisions-web per stats_decision_record=no. just check 5d0bbc111784c689e7cb71946afadb8c still red on docs-gen-check (0.40.1 wrap), docs-lint E5 on unrelated pages, and full-suite agent-display tests after core-identity-changed — recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1m3.8](sase-1m3.8.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.3/README.md) | [sase-1m3.3](sase-1m3.3.md) | 0 |
