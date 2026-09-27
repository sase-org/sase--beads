# Bead: sase-1bc.6.1.1 — Flag, ace.agent\_tabs config, machine mode, and the tab index model

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.1` · **Size:** medium
**Created:** 2026-09-27 13:46:07 EDT · **Closed:** 2026-09-27 14:04:32 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

tab-foundation: create the agent_tabs beta flag with sase flag new and a single check helper; add the ace.agent_tabs typed reader, schema, defaults, and docs; add the token-cached machine-mode accessor; extend the core adapter with typed tab keys and a batched catalog wrapper; give clan containers an agent_tab; build the pure, memoized per-root tab index model with tests. No UI wiring.

## Notes

[2026-09-27T18:04:16Z · sase-1bc.6.1.1] PROPOSED FOLLOW-UP: symvision lint fails on clean base tree too (usage_windows.py telegram pragmas reference missing sase-telegram symbols); fails just check identically without this phase change

[2026-09-27T18:04:32Z · sase-1bc.6.1.1] tab-foundation done: agent_tabs beta flag registered (bead sase-1be) with schema regen and docs row; ace.agent_tabs settings+schema+defaults+docs; token-cached machine-mode view config; AgentTabKey/tokens/batched catalog adapter; clan and imported-session container tab inheritance; pure memoized tab index model. Verified: 68 new tests pass; targeted suites pass (config-schema, feature_flags, clan/imported-session, tribe display, tab directive: 340 total); sase tool run check lints pass except a symvision failure that reproduces identically on the clean base tree (recorded as PROPOSED FOLLOW-UP). No UI wiring; nothing user-visible changed.

## Dependencies

- **Blocks:** [sase-1bc.6.1.2](sase-1bc.6.1.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.1/README.md) | [sase-1bc.6.1.1](sase-1bc.6.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ad9637`](https://github.com/sase-org/sase/commit/8ad96371875bd3fb3fdad763a32e2751e0bd218a) | feat(agent-tabs): tab-foundation flag, config, machine mode, and tab index model (sase-1bc.6.1.1) | [sase-1bc.6.1.1](sase-1bc.6.1.1.md) | 2026-09-27 14:06:56 EDT |
