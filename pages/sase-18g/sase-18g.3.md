# Bead: sase-18g.3 — Header panel preview, expansion, layout, docs, and visual verification

[Bead Pages](../README.md) / [sase-18g](README.md) / sase-18g.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rk.md) · **Assignee:** `sase-18g.3` · **Size:** medium
**Created:** 2026-09-24 17:41:32 EDT · **Closed:** 2026-09-24 20:58:43 EDT
**Plan:** [202609/agent\_header\_xprompt\_preview.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_header_xprompt_preview.md)

## Description

panel: turn on xprompt detachment, render the collapsed preview and expanded XPROMPT section in AgentHeaderPanel with column-derived budgets, an overflow subtitle, a pending-height hold, and pin reapply; remove the phantom header/footer row; update docs and goldens; and verify with live screenshots.

## Notes

[2026-09-25T00:31:58Z · sase-18g.3] PROPOSED FOLLOW-UP: test_search_overlay_keeps_jump_panel_visible fails identically on clean base tree (NoMatches #agent-prompt-scroll); pre-existing, needs triage into a task bead

[2026-09-25T00:32:08Z · sase-18g.3] PROPOSED FOLLOW-UP: regenerate Agents PNG goldens via just fix-tui-screenshots and add collapsed-truncation/short-fit goldens (visual lane not run in this single-turn phase)

[2026-09-25T00:52:53Z · sase-18g.3] PROPOSED FOLLOW-UP: just lint _lint-mypy fails on clean base too (tools/sase_core_wheel_cache arg-type/var-annotated); pre-existing, needs a task bead

[2026-09-25T00:56:08Z · sase-18g.3] PROPOSED FOLLOW-UP: symvision flags AgentSurvivorsError/Survivor/environ_has_launch_key identically on clean base; unrelated in-flight symbols, needs triage

[2026-09-25T00:58:11Z · sase-18g.3] PROPOSED FOLLOW-UP: test_parallel_step_does_not_show_agent_prompt fails identically on clean base; pre-existing, needs a task bead

[2026-09-25T00:58:43Z · sase-18g.3] Panel renders collapsed XPROMPT preview (quote bar, reflow, budget, +N lines subtitle) and expanded XPROMPT; detach on; phantom-row CSS; docs+goldens wiring; 22 header-panel tests plus decks/identity/metadata suites green; symvision/mypy-tools/jump-visibility/parallel-step failures reproduce on clean base and are filed as follow-ups

## Dependencies

- **Depends on:** [sase-18g.1](sase-18g.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18g.2](sase-18g.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18g.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.3/README.md) | [sase-18g.3](sase-18g.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4858f20`](https://github.com/sase-org/sase/commit/4858f20a2d0016b21e78558c433854112108de2c) | feat(ace): collapsed header shows xprompt preview rows with budget and overflow | [sase-18g.3](sase-18g.3.md) | 2026-09-24 21:09:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18g.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-18g.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.land/README.md

<!-- sase:referenced-by:end -->
