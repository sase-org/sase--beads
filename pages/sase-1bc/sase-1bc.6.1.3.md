# Bead: sase-1bc.6.1.3 — Tab switching, persistence, keys, minimal strip, and perf metric

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.3` · **Size:** medium
**Created:** 2026-09-27 13:46:10 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

tab-state-keys: add the synchronous tab switch with per-tab memory, startup selection, the emptied-tab latch, and the disappearance fallback; persist the active key off-thread; wire ]/[ next/prev_agents_tab and unbound pick_agents_tab through the full keymap surface, with legacy bracket yield; render a labels-only PanelTabStrip in #agents-header; add the tab-switch perf metric and AcePage state.

## Dependencies

- **Depends on:** [sase-1bc.6.1.2](sase-1bc.6.1.2.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.4](sase-1bc.6.1.4.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.5](sase-1bc.6.1.5.md) ◐ · ⧖ 2026-09-27
