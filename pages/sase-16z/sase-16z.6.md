# Bead: sase-16z.6 — Dedicated \`usage\` scheduler routine that probes inline

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.6` · **Size:** medium
**Created:** 2026-09-23 11:06:15 EDT · **Closed:** 2026-09-23 15:13:57 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

usage-routine: move `usage_refresh` out of `checks` into a new 60 s `usage` routine whose job runs the admitted batch in-process under non-proc operation IDs. Store-based waiting replaces proc waits for joiners (CLI and Models panel). The TUI fallback runs only when the scheduler does not own collection, `u` toasts render real receipt reasons, and the tests and docs are updated to match.

## Notes

[2026-09-23T19:12:21Z · sase-16z.6] PROPOSED FOLLOW-UP: privatize or delete ClanSummaryDigest in prompt_panel/_agent_tribe_clan_summaries.py (symvision unused-public; in-file use only)

[2026-09-23T19:12:52Z · sase-16z.6] PROPOSED FOLLOW-UP: privatize or delete MemberJumpSection in prompt_panel/_member_roster.py (symvision unused-public since sase-16y closed)

[2026-09-23T19:13:22Z · sase-16z.6] PROPOSED FOLLOW-UP: privatize resolve_provider_cli_command in usage/_probe_meta.py to its in-file caller and sase-16z.5 tests (symvision unused-public)

[2026-09-23T19:13:57Z · sase-16z.6] usage-routine done: 60s usage routine probes inline (no periodic procs); store joins for CLI/Models; scheduler-gated TUI fallback; reason-aware toasts; 112 touched-area tests green, ruff+mypy green; just-check symvision red only on 3 pre-existing foreign symbols (follow-ups noted)

## Dependencies

- **Depends on:** [sase-16z.5](sase-16z.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.7](sase-16z.7.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.6/README.md) | [sase-16z.6](sase-16z.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a6e2758`](https://github.com/sase-org/sase/commit/a6e27583c848ef087636e9f4fca1f2bd027c6bda) | feat(llm-provider): dedicated usage scheduler routine that probes inline | [sase-16z.6](sase-16z.6.md) | 2026-09-23 15:15:21 EDT |
