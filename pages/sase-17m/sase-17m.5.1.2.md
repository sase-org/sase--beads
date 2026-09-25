# Bead: sase-17m.5.1.2 — Agents actions, folding, navigation, and preview warmup

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.2` · **Size:** medium
**Created:** 2026-09-25 00:06:03 EDT · **Closed:** 2026-09-25 01:52:55 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

actions: rename actions/agents/_loading_family_previews.py and its mixin methods. Rename the trace span agents.family_plan_preview_warmup to agents.agent_session_plan_preview_warmup and the task sase-agents-family-previews to sase-agents-session-previews. Change the fold and navigation kind value "family" to "session" and rename the family identifiers in actions/agents, actions/navigation, actions/agent_workflow, and the other ACE action and app modules. Rename the perf scenarios family_container_press and family_container_unfolded_press to session_container_*, along with their baselines and bench assertions. Update the tests for all of these.

## Notes

[2026-09-25T05:52:25Z · sase-17m.5.1.2] PROPOSED FOLLOW-UP: `sase tool run check` (runs c3e1dc695d648c204d480b9206840964 and 9497b4401daf997e756ef141e375f77f) consistently fails Symvision on untouched `CdResolution` in `src/sase/ace/tui/command_line/builtins.py` and `PathCompletionRequest` in `src/sase/ace/tui/command_line/sources.py`; every preceding check stage passed.

[2026-09-25T05:52:55Z · sase-17m.5.1.2] Renamed the Agents preview-warmup module/mixin/task/span to agent-session terminology; migrated action, fold/navigation internal kind values, notification helpers, matching action tests, and perf scenarios/baselines to session terminology. Verified `just fix`, 783 focused action/folding/navigation/perf tests, and 67 post-boundary keybinding/fold tests passed; `sase bead epic-symbols sase-17m.5.1.2` reported no entries. `sase tool run check` passed all stages before Symvision’s pre-existing failures on untouched CdResolution and PathCompletionRequest; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-17m.5.1.1](sase-17m.5.1.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.3](sase-17m.5.1.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.2/README.md) | [sase-17m.5.1.2](sase-17m.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`61d3b27`](https://github.com/sase-org/sase/commit/61d3b2707c2a669a0f173a6288a03cea3ceb2278) | refactor(agent-session): rename ACE action session surfaces (sase-17m.5.1.2) | [sase-17m.5.1.2](sase-17m.5.1.2.md) | 2026-09-25 01:54:07 EDT |
