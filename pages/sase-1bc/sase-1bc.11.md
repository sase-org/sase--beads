# Bead: sase-1bc.11 — Move agents between tabs

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.11` · **Size:** medium
**Created:** 2026-09-27 10:57:16 EDT · **Closed:** 2026-09-28 09:01:28 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

tab-moves: add persist-directive agent_tab support (meta, prompt, clan record), the sase agent tab list/set/unset CLI, and a Tribe & Tab N modal with optimistic moves; disable moves on remote rows.

## Notes

[2026-09-28T13:01:11Z · sase-1bc.11] PROPOSED FOLLOW-UP: clan-record clan_tab needs a sase-core schema change — the record_agent_clan_attributes binding silently drops an unknown tab key (verified: changed=False, no tab stored), so tab moves persist agent_tab/agent_tab_source=moved on root meta + %tab prompt rewrite, which is what display resolution and launch validation actually read

[2026-09-28T13:01:28Z · sase-1bc.11] tab-moves done: sase agent tab list/set/unset CLI (root-wide meta+prompt moves, JSON list via core catalog), persist-directive set_tab mutator (+tab composition on tribe kinds), Tribe & Tab N modal (completion, optimistic+rollback, remote refusal 'tab moves run on the owning machine', Moved-toast, index refresh), docs cli.md/agent_sessions.md. Verified: all lint gates pass (tool run 2bbb7abd), 224 affected-area tests pass incl 8 new in tests/test_agent_tab_moves.py

## Dependencies

- **Blocks:** [sase-1bc.12](sase-1bc.12.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.6](sase-1bc.6.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.11/README.md) | [sase-1bc.11](sase-1bc.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`647e053`](https://github.com/sase-org/sase/commit/647e053e94e46b0d2e34bcd083e777113ce2ce24) | feat(agents): add tab moves via CLI, persist directive, and TUI modal | [sase-1bc.11](sase-1bc.11.md) | 2026-09-28 09:05:28 EDT |
