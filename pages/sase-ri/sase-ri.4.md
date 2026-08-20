# Bead: sase-ri.4 — Build and integrate the nested Config catalog

[Bead Pages](../README.md) / [sase-ri](README.md) / sase-ri.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rd.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rd.land.w1.md) · **Assignee:** `sase-ri.4` · **Size:** medium
**Created:** 2026-08-20 12:43:01 EDT · **Closed:** 2026-08-20 15:07:27 EDT
**Plan:** [202608/admin\_center\_config\_catalog.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_config_catalog.md)

## Description

config_hub: add the lazy Config sub-tab host, move every requested surface into it, and route contextual prompt entry through a guarded integration path.

## Notes

[2026-08-20T19:06:45Z · sase-ri.4] PROPOSED FOLLOW-UP: Isolate completion/TUI/suite-gate flakes under concurrent full-suite load — just check escalated (Justfile + schema) and failed tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration, tests/ace/tui/modals/test_snippet_name_modal.py::{test_elsewhere_collision_loads_other_template_but_keeps_destination,test_matches_filter_order_and_tab_completion}, and tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed; each exact quoted rerun passed.

[2026-08-20T19:07:27Z · sase-ri.4] Created beta flag admin_center_config_hub (bead sase-rk) and the lazy ConfigHubPane: six-section Admin Center when enabled (XPrompts nested as the default Config child), seven-section plus standalone prompt panels when disabled. Verified both flag states (catalog, resume mapping xprompts->config, prompt shortcuts, lazy/cached/failed mounts, [ ] cycling, Tab arbitration); just check lint/validate passed and scoped tests escalated to the full suite (Justfile+schema) with only unrelated contention flakes whose exact reruns passed. No --epic-symbol leftovers.

[2026-08-20T19:08:51Z · sase-ri.4] Created beta flag admin_center_config_hub (bead sase-rk) and the lazy ConfigHubPane: six-section Admin Center when enabled (XPrompts nested as the default Config child), seven-section plus standalone prompt panels when disabled. Verified both flag states (catalog, resume mapping xprompts->config, prompt shortcuts, lazy/cached/failed mounts, [ ] cycling, Tab arbitration); just check lint/validate passed and scoped tests escalated to the full suite (Justfile+schema) with only unrelated contention flakes whose exact reruns passed. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-ri.1](sase-ri.1.md) ✓ · ⧖ 2026-08-20
- **Depends on:** [sase-ri.2](sase-ri.2.md) ✓ · ⧖ 2026-08-20
- **Depends on:** [sase-ri.3](sase-ri.3.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-ri.5](sase-ri.5.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ri.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.4/README.md) | [sase-ri.4](sase-ri.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1382a43`](https://github.com/sase-org/sase/commit/1382a43d8c5fedeb5d09b95df089c692a3e6cbcc) | feat(ace): nest Admin Center config tools behind a beta flag | [sase-ri.4](sase-ri.4.md) | 2026-08-20 15:09:49 EDT |
