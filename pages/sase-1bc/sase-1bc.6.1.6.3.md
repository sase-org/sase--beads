# Bead: sase-1bc.6.1.6.3 — Honest marked and custom scope wording, docs accuracy, and symvision cleanup

[Bead Pages](../README.md) / [sase-1bc.6.1.6](sase-1bc.6.1.6.md) / sase-1bc.6.1.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) · **Assignee:** `sase-1bc.6.1.6.3` · **Size:** medium
**Created:** 2026-09-27 20:11:38 EDT · **Closed:** 2026-09-28 02:45:47 EDT
**Plan:** [202609/agent\_tabs\_scope\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md)

## Description

scope-wording-and-symbols: count the "N of M marked agents are on other tabs" line over one consistent set; make the custom cleanup header name the active tab; correct the docs/ace.md agent-tabs note and the flag table wording; resolve every symvision-flagged public symbol this epic added (privatize, delete, or re-key to a still-open sase-1bc phase), so no agent-tabs symbol remains in the symvision output.

## Notes

[2026-09-28T05:59:45Z · sase-1bc.6.1.6.3] Verified: marked N/M counted over original marks (off-tab clan container is 1 of 1; mixed local+remote is 1 of 2); custom cleanup header uses bulk scope label (on <tab>, across all tabs only at ALL_AGENT_TABS); docs/ace.md Agent Tabs note sits next to Machines and states machine-mode-only per-machine remote tabs; flag table matches registry [/] wording; just _lint-symvision clean with no agent-tabs unused-public symbols; sase bead epic-symbols sase-1bc.6.1.6.3 has no leftovers. tests/ace/tui/test_agent_tab_scope_honesty.py 18 passed.

[2026-09-28T06:22:40Z · sase-1bc.6.1.6.3--1] PROPOSED FOLLOW-UP: just check still fails test_no_system_clock_display_sites (KNOWN, sase-1bp) — update_gear.py:80/81/111, update_panel_state.py:142/143, plus view_vocabulary.py:131 from sase-1bt.3; reproduces on clean base, outside this phase

[2026-09-28T06:45:47Z · sase-1bc.6.1.6.3--2] Verified: marked N/M counted over original marks (off-tab clan container is 1 of 1; mixed local+remote is 1 of 2); custom cleanup header uses bulk scope label (on <tab>, across all tabs only at ALL_AGENT_TABS); docs/ace.md Agent Tabs note sits next to Machines and states machine-mode-only per-machine remote tabs; flag table matches registry [/] wording; sase bead epic-symbols has no leftovers. just check: 2202 passed, 1 KNOWN (test_no_system_clock_display_sites, sase-1bp, reproduces on clean base).

## Dependencies

- **Depends on:** [sase-1bc.6.1.6.1](sase-1bc.6.1.6.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.6.1.6.2](sase-1bc.6.1.6.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.6.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.6.3.md) | [sase-1bc.6.1.6.3](sase-1bc.6.1.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d094fe7`](https://github.com/sase-org/sase/commit/d094fe70ee7f98cb9242575bd5757c85c2a33091) | fix(ace-tui): make agent-tab bulk wording honest and align tab docs | [sase-1bc.6.1.6.3](sase-1bc.6.1.6.3.md) | 2026-09-28 02:48:46 EDT |
