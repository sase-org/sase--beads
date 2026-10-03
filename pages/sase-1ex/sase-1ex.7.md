# Bead: sase-1ex.7 — One highlight build and no pump-side Jinja inspect per cycle edit

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.7` · **Size:** medium
**Created:** 2026-10-02 14:53:52 EDT · **Closed:** 2026-10-03 06:54:51 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

cycle-edit-coalesce: batch highlight-map builds so a cycle edit pays for one. Make the queued Changed/SelectionChanged context refreshes no-ops when nothing changed, skip the needless arg-hint refresh, and move the Jinja diagnostics inspect into a pump-free task.

## Notes

[2026-10-03T10:54:14Z · sase-1ex.7] PROPOSED FOLLOW-UP: bench before/after comparison for cycle-edit-coalesce not recorded — after-numbers only (single_ctrl_p hdl 1.36ms, burst hdl p95 1.24ms); rerun bench_prompt_bar_keys against pre-phase base in a clean worktree to quantify the expected -10 to -20ms delta

[2026-10-03T10:54:26Z · sase-1ex.7] PROPOSED FOLLOW-UP: src/sase/core/publication_payload_facade.py + tests/test_core_publication_payload.py landed under stitch 5c7e7514ae tagged sase-1ex.7 but belong to the publication/publish track (see read-by agent:sase-1eq.3.1.land) — land agent to confirm ownership, do not touch from this phase

[2026-10-03T10:54:51Z · sase-1ex.7] cycle-edit-coalesce verified: 8/8 test_cycle_edit_coalesce.py pass (one build per ctrl+p, span parity, echo no-op, nested batch, jinja off-pump + stale-drop, wire memo 1 call, arg-hint pre-check); neighbors green (jinja/todo-title/publication-payload 24 pass); sase tool run check verdict no_new_failures (800 pass, 1 KNOWN pre-existing with witness); bench after-numbers single_ctrl_p hdl 1.36ms / burst hdl p95 1.24ms (target sync handler <=5ms met); epic-symbols clean; 2 PROPOSED FOLLOW-UP notes recorded (bench base comparison, publication_payload ownership)

## Dependencies

- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.2](sase-1ex.2.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.6](sase-1ex.6.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.7.md) | [sase-1ex.7](sase-1ex.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c7e751`](https://github.com/sase-org/sase/commit/5c7e7514ae47c29879e9dc122e43948b2984c631) | fix(ace-tui): repair cycle-edit-coalesce verification gates (sase-1ex.7) | [sase-1ex.7](sase-1ex.7.md) | 2026-10-02 21:28:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.7--1][1] | check stray publication_payload ownership | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.7.md

<!-- sase:referenced-by:end -->
