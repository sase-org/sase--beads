# Bead: sase-1cj.2 — Record typed vs generated origin on prompt history rows

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.2` · **Size:** medium
**Created:** 2026-09-29 07:14:27 EDT · **Closed:** 2026-09-29 07:42:25 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

prompt-origin: add an optional origin field (typed or generated) to PromptEntry, round-trip it through shard I/O with typed-wins merge rules, and thread it from every launch write site so the prediction corpus can exclude machine-generated prompts.

## Notes

[2026-09-29T11:42:04Z · sase-1cj.2] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-1be (key agent_tabs, no registry definition, opened 2026-09-27) — pre-existing tracker state, reproduces independent of the prompt-origin diff which adds no flags

[2026-09-29T11:42:25Z · sase-1cj.2] prompt-origin done: PromptEntry.origin (typed/generated/None) round-trips through shard I/O with typed-wins merge in _apply_prompt_mutations, dedup, and rewrite; origin threads through launch_agents_from_cwd/single/fanout/bead-work plumbing with typed at TUI-submit/sase-run/mobile/cancel/stash sites and generated at LaunchApproval/admission/plan-approval/restart/chop/bead-work sites plus SASE_AGENT forcing; verified by new tests/history/test_prompt_origin.py (9 tests) plus ~450 related tests green (history, chop, restart, admission, mobile, bead-work); just check passes ruff/mypy/fmt with only the pre-existing sase-1be flag-bead failure recorded as follow-up

## Dependencies

- **Blocks:** [sase-1cj.5](sase-1cj.5.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.2/README.md) | [sase-1cj.2](sase-1cj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eaa4aa4`](https://github.com/sase-org/sase/commit/eaa4aa4aa72d67f27156e22cd7939422e87f4afc) | feat(prompt-history): record typed vs generated origin on prompt rows | [sase-1cj.2](sase-1cj.2.md) | 2026-09-29 07:44:59 EDT |
