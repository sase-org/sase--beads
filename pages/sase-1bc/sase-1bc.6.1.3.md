# Bead: sase-1bc.6.1.3 — Tab switching, persistence, keys, minimal strip, and perf metric

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.3` · **Size:** medium
**Created:** 2026-09-27 13:46:10 EDT · **Closed:** 2026-09-27 17:21:08 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

tab-state-keys: add the synchronous tab switch with per-tab memory, startup selection, the emptied-tab latch, and the disappearance fallback; persist the active key off-thread; wire ]/[ next/prev_agents_tab and unbound pick_agents_tab through the full keymap surface, with legacy bracket yield; render a labels-only PanelTabStrip in #agents-header; add the tab-switch perf metric and AcePage state.

## Notes

[2026-09-27T21:20:38Z · sase-1bc.6.1.3] PROPOSED FOLLOW-UP: symvision gate fails on src/sase/integrations/usage_windows.py sase-telegram pragma refs; reproduces identically on clean base tree (verified via stash + just _lint-symbols run, exit 1, same 4 errors)

[2026-09-27T21:20:52Z · sase-1bc.6.1.3] PROPOSED FOLLOW-UP: live flag-on two-tab screenshot + instant-switch evidence deferred to sase-1bc.6.1.5 scope-honesty verification (needs a live two-tab roster; unit perf-wiring test covers the agents_tab_switch sample here)

[2026-09-27T21:21:08Z · sase-1bc.6.1.3] tab-state-keys done: sync switch with per-tab memory, startup/persisted/attention startup order, emptied-tab latch, machine-gone fallback toast, off-thread token persistence, ]/[ + pick_agents_tab full keymap surface with legacy bracket yield, minimal PanelTabStrip in #agents-header, agents_tab_switch perf sample, AcePage state. Verified: 18 new switch tests + updated bracket tests green (97 tab tests, 198 keymap/command/footer tests green), just fmt/ruff/mypy clean; symvision fails identically on clean base (pre-existing usage_windows/sase-telegram, filed as follow-up); no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1bc.6.1.2](sase-1bc.6.1.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.4](sase-1bc.6.1.4.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.5](sase-1bc.6.1.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.3/README.md) | [sase-1bc.6.1.3](sase-1bc.6.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c78eb38`](https://github.com/sase-org/sase/commit/c78eb3805faaa4848aa7e8afea69364e2018f064) | feat(agent-tabs): tab switching, persistence, keys, minimal strip, and perf metric (sase-1bc.6.1.3) | [sase-1bc.6.1.3](sase-1bc.6.1.3.md) | 2026-09-27 17:22:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.6.1.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.3/README.md

<!-- sase:referenced-by:end -->
