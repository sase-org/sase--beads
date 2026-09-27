# Bead: sase-1bc.6.1.2 — Active-tab scope stage and tab-keyed panel state

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.2` · **Size:** medium
**Created:** 2026-09-27 13:46:08 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

scope-stage: cache the tab-independent query result and add the active-tab scope stage in the inline and worker finalize paths; add the scope to PreparedApplySnapshot and the stale token; route every direct _agents mutation through the cached result; key the panel-index memo, AgentPanelFoldScope (fold persistence v3 to v4), session-sticky panels, and selection memory by tab scope.

## Dependencies

- **Depends on:** [sase-1bc.6.1.1](sase-1bc.6.1.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.3](sase-1bc.6.1.3.md) ◐ · ⧖ 2026-09-27
