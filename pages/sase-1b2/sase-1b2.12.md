# Bead: sase-1b2.12 — Python run-view facade, artifact collector, and end-to-end proof

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.12` · **Size:** medium
**Created:** 2026-09-27 05:49:44 EDT · **Closed:** 2026-09-27 08:24:19 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

run-view-adapter: move the pin past core-run-view-detail and add the typed finalizer_run_view facade and binding-guard registrations. Add a TUI-agnostic capped artifact collector with liveness facts and stat signatures, and an end-to-end test that drives the real controller and executors into the projection.

## Notes

[2026-09-27T12:23:39Z · sase-1b2.12] PROPOSED FOLLOW-UP: just check stays red on the clean base tree for pre-existing gates unrelated to this phase: symvision private-misuse _root_represents_member (agent_session_members vs _meta_enrichment_status), toobig src/sase/tool/executor.py over 1000 lines (tracked by sase-1a9), mypy 5 errors in agent_bundle/agent_groups/_tree/_agent_display_hint_sections (see sase-1b2.6 note), and check_sase_core_rs_bindings missing proc_wire_schema_version

[2026-09-27T12:24:19Z · sase-1b2.12] run-view-adapter done: pin 912331c (past core-run-view-detail), rebuilt wheel, project_finalizer_node_view facade + tolerant typed view, capped collector (plan-envelope unwrap, 4MiB/1MiB/64KiB/16KiB/4KiB ceilings, stat-only signature) + node_run_targets. Verified: 12 new e2e tests green (success, fail-retry-pass with superseded diagnostics, deferral, handoff skip, kill-interrupted with live tail, plugin steps) plus 127 neighboring finalizer/TUI tests green; ruff/fmt/keep-sorted/scoped-mypy/validate_sase_core_rs clean. Pre-existing clean-tree failures (symvision private-misuse, toobig executor.py=sase-1a9, 5 mypy errors, proc_wire_schema_version) recorded as PROPOSED FOLLOW-UP; no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1b2.13](sase-1b2.13.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.14](sase-1b2.14.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.3](sase-1b2.3.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.6](sase-1b2.6.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.7](sase-1b2.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.12/README.md) | [sase-1b2.12](sase-1b2.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65c016a`](https://github.com/sase-org/sase/commit/65c016a8973dccf28ee71f17f004fdd3f3bde566) | feat(finalizers): add run-view adapter over core detail binding | [sase-1b2.12](sase-1b2.12.md) | 2026-09-27 08:26:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.12][2] | Need phase scope and design file | 2 |
| read-by | [agent:sase-1b2.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.12/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.land/README.md

<!-- sase:referenced-by:end -->
