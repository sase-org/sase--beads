# Bead: sase-16y.3 — Jump panel widget, layout, toggle, narrowing, and visual verification

[Bead Pages](../README.md) / [sase-16y](README.md) / sase-16y.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q0.md) · **Assignee:** `sase-16y.3` · **Size:** medium
**Created:** 2026-09-23 10:49:58 EDT · **Closed:** 2026-09-23 13:45:48 EDT
**Plan:** [202609/agent\_jump\_footer\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_jump_footer_panel.md)

## Description

panel: add the AgentJumpPanel widget as the last child of the detail column, wire the sink, visibility, dot toggle, bottom-pin handling, and first-digit narrowing, add CSS, help and docs, pilot/reliability/visual tests, live screenshot review, and the Agents golden refresh.

## Notes

[2026-09-23T17:45:02Z · sase-16y.3] PROPOSED FOLLOW-UP: retry_e2e PNG goldens drift per environment — countdown/completed_chain/running_fallback mismatch on pristine master in this workspace (fakey artifact content hashes) while CI stays green; refresh kept panel-only updates, reverted 3 hash-only ones

[2026-09-23T17:45:48Z · sase-16y.3] AgentJumpPanel widget + AgentDetail wiring + narrowing hooks + CSS + help/docs landed and verified: 23 pilot/hook/reliability tests pass (empty/non-roster/all-unnumbered hidden; family/clan/tribe/neighbors shown; toggle/persist/geometry-in-5-layouts/search/hints/pin/2-digit-narrow/scroll-reset/availability), 36 legend tests pass incl. narrow-span regression (fixed hand-clipped spans crashing Rich), 6 new PNG goldens created and visually reviewed, full screenshot refresh applied 61 panel-only updates (16 renders inspected, bbox-audited all 64; 3 hash-only retry goldens reverted as pre-existing env drift), gate-shell test viewport assertion fixed, just check green except pre-existing sase-16u symvision symbol (untouched, other epic); 3 legend epic-symbols consumed, MemberJumpSection stays whitelisted under open parent sase-16y

## Dependencies

- **Depends on:** [sase-16y.1](sase-16y.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16y.2](sase-16y.2.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16y.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.3/README.md) | [sase-16y.3](sase-16y.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`311e761`](https://github.com/sase-org/sase/commit/311e761145e56aa22b2b4eaa030afd3ebd704932) | feat(ace): sticky collapsible jump footer panel on the Agents tab | [sase-16y.3](sase-16y.3.md) | 2026-09-23 13:51:47 EDT |
