# Bead: sase-1ca.2 — Hard pytest boundary on the prompt stash and prompt history stores

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.2` · **Size:** small
**Created:** 2026-09-28 17:30:10 EDT · **Closed:** 2026-09-28 17:43:28 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

guard-prompt-stores: route every prompt_stash_facade read/mutation and every prompt-history write through assert_test_state_write_isolated so pytest can never touch the account's real prompts, with tests.

## Notes

[2026-09-28T21:42:57Z · sase-1ca.2] PROPOSED FOLLOW-UP: tests/ace/tui/actions/test_agent_loader_phase5_index_wiring.py (2 tests) and test_agent_search_history_split.py::test_bounded_agents_viewport_expands_near_prefix_end fail identically on clean base tree — pre-existing, unrelated to guard-prompt-stores

[2026-09-28T21:43:09Z · sase-1ca.2] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on base: closed flag bead sase-1be still has surviving agent_tabs definition — pre-existing, blocks the check gate for all phase workers

[2026-09-28T21:43:28Z · sase-1ca.2] Guarded all 10 prompt_stash_facade functions and prompt-history writers (save_shard, save_prompt_history, locked_prompt_history) with assert_test_state_write_isolated; added 4 guard tests to tests/test_state_write_guard.py (17/17 pass); scoped the monkeypatch.undo() landmine in test_failed_read_clears_flags_next_opens to monkeypatch.context(); stash/restore/trash/history suites green (1204 passed; 3 agent-loader failures and the lint-flags failure reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UPs); ruff/mypy/fmt/keep-sorted pass

## Dependencies

- **Blocks:** [sase-1ca.6](sase-1ca.6.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.2/README.md) | [sase-1ca.2](sase-1ca.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ca.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.2/README.md

<!-- sase:referenced-by:end -->
