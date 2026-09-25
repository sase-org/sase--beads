# Bead: sase-17x.13.10 — Close the \`:\` Command Line landing gaps: hide/hop deadlocks, key and source bugs, stale goldens

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.10

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.land`
**Created:** 2026-09-25 08:41:39 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

The `:` Command Line from epics sase-17x and sase-17x.13 hides, hops, and reopens without wedging the app. Every configurable key routes through `ace.keymaps.command_line`. Completion sources return fresh, complete candidates. No state mutation or disk write runs on the wrong thread. `just lint` passes the line-count gate. Every golden this epic changed is regenerated and inspected, and a live walkthrough succeeds end to end, including a screenshot export after hide and reopen.

## Notes

[2026-09-25T13:53:07Z · sase-17m.5.1.6.land] DISCOVERED ISSUE: proposed by sase-17m.5.1.6.2 note #2. Its agents_decks_single_empty, agents_onboarding, and agents_onboarding_no_plugins PNG goldens drift with the 'Command Line: run sase commands without leaving the TUI.' tip, unrelated to the agent-session rename. Your golden phase already owns five onboarding goldens; include these three in that review and accept only explained diffs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.land/README.md) | [sase-17x.13.10](sase-17x.13.10.md) | 0 |
