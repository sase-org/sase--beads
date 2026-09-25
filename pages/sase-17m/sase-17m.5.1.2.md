# Bead: sase-17m.5.1.2 — Agents actions, folding, navigation, and preview warmup

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.2` · **Size:** medium
**Created:** 2026-09-25 00:06:03 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

actions: rename actions/agents/_loading_family_previews.py and its mixin methods. Rename the trace span agents.family_plan_preview_warmup to agents.agent_session_plan_preview_warmup and the task sase-agents-family-previews to sase-agents-session-previews. Change the fold and navigation kind value "family" to "session" and rename the family identifiers in actions/agents, actions/navigation, actions/agent_workflow, and the other ACE action and app modules. Rename the perf scenarios family_container_press and family_container_unfolded_press to session_container_*, along with their baselines and bench assertions. Update the tests for all of these.

## Dependencies

- **Depends on:** [sase-17m.5.1.1](sase-17m.5.1.1.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.3](sase-17m.5.1.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.2/README.md) | [sase-17m.5.1.2](sase-17m.5.1.2.md) | 0 |
