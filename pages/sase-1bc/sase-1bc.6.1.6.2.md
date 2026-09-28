# Bead: sase-1bc.6.1.6.2 — Back-anchors, failed-reveal restore, and fold-aware reveal for every cross-tab jump

[Bead Pages](../README.md) / [sase-1bc.6.1.6](sase-1bc.6.1.6.md) / sase-1bc.6.1.6.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) · **Assignee:** `sase-1bc.6.1.6.2` · **Size:** medium
**Created:** 2026-09-27 20:11:31 EDT
**Plan:** [202609/agent\_tabs\_scope\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md)

## Description

cross-tab-jump-repairs: save the back-anchor before switching tabs in _try_reveal_agent_row; drop the notification pre-switch in favor of the Node Finder ladder; route the run-log, revive, Files, and link-trail jumps through the fold-expanding reveal with tab restore; restore the tab when a back-jump or a last-launch reveal fails; make the ,j off-tab path reveal-aware; show the off-tab chip on every off-tab Node Finder row; keep flag-off lookups unchanged; add tests for every entry point.

## Dependencies

- **Depends on:** [sase-1bc.6.1.6.1](sase-1bc.6.1.6.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.6.3](sase-1bc.6.1.6.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.6.2/README.md) | [sase-1bc.6.1.6.2](sase-1bc.6.1.6.2.md) | 0 |
