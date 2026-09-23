# Bead: sase-171.2 — Install flow in the Updates tab

[Bead Pages](../README.md) / [sase-171](README.md) / sase-171.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q6.md) · **Assignee:** `sase-171.2` · **Size:** medium
**Created:** 2026-09-23 11:58:16 EDT · **Closed:** 2026-09-23 14:25:51 EDT
**Plan:** [202609/updates\_tab\_agent\_cli\_install.md](https://github.com/sase-org/sase--plans/blob/main/202609/updates_tab_agent_cli_install.md)

## Description

tui-install: give missing agent-CLI rows an install verb on i / Space / I, a redesigned install detail panel, a digest-bearing confirm preview, a tracked sequential install proc, one combined flow for mixed plugin + CLI marks, install-aware history, result lines, and toasts, plus tests, docs, and goldens.

## Notes

[2026-09-23T18:24:54Z · sase-171.2] PROPOSED FOLLOW-UP: symvision flags unused public ClanSummaryDigest in prompt_panel/_agent_tribe_clan_summaries.py (landed in e1c4208cd, untouched by this phase) — blocks just check

[2026-09-23T18:25:51Z · sase-171.2] tui-install done: CLI install verb on i/Space/I, digest-bearing confirm preview, tracked sequential proc (ADMIN_CENTER), combined plugin+CLI flow (CLIs first, restart only on plugin change), install-aware history/result lines/toasts, 21 new + extended tests green, docs updated, 4 new + 20 refreshed PNG goldens inspected and serial-check clean; full just check green except pre-existing ClanSummaryDigest symvision failure (noted as follow-up)

## Dependencies

- **Depends on:** [sase-171.1](sase-171.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-171.3](sase-171.3.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-171.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-171.2/README.md) | [sase-171.2](sase-171.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02cd6b6`](https://github.com/sase-org/sase/commit/02cd6b69ee2b587e118482877d6719bebb8eda31) | feat(ace): implement Updates-tab agent-CLI install flow | [sase-171.2](sase-171.2.md) | 2026-09-23 14:28:37 EDT |
