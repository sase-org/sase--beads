# Bead: sase-o8.3 — Relation, recency, and frequency scoring

[Bead Pages](../README.md) / [sase-o8](README.md) / sase-o8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.3` · **Size:** medium
**Created:** 2026-08-17 06:01:53 EDT · **Closed:** 2026-08-17 07:43:42 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

ranking: add the pure scoring engine that turns the placeholder context store plus the prompt being edited into ranked placeholders with per-signal contributions, a dominant reason, and the evidence each row displays.

## Notes

[2026-08-17T11:43:19Z · sase-o8.3--1] PROPOSED FOLLOW-UP: flake in test_drain_config_token_refresh_joins_worker_and_advances_epoch — just check-full (31880 passed, 1 failed) asserted current_config_token() == ("token", 1) but got a process-identity cache key (pid=4122, cwd=workspace, sase.yml mtime); isolated rerun passed in 1.28s. Unrelated to placeholder ranking.

[2026-08-17T11:43:42Z · sase-o8.3--1] Shipped the pure ranking engine (RankedPlaceholder, build_placeholder_ranking_context, rank_common_placeholders, rank_recent_common_placeholders) with 0.50/0.30/0.20 weights, 14-day recency half-life, capped-lift relation + shrinkage, and CommonPlaceholderIndex._ranking_memo. prompt_context_tokens is public so ranking and recording share one tokenizer. tests/history/test_prompt_placeholder_ranking.py covers plan cases. just lint green; ranking+placeholder tests 48/48. Justfile --epic-symbol entries for the four o8.3 APIs; load_common_placeholder_index retargeted from closed sase-o8.2 to sase-o8.4. just check-full: 31880 passed, 11 skipped; one unrelated flake in test_drain_config_token_refresh_joins_worker_and_advances_epoch (process-identity cache key vs mocked token) that passed isolated — recorded as PROPOSED FOLLOW-UP.

[2026-08-17T11:44:57Z · sase-o8.3--1] Pure ranking engine shipped: RankedPlaceholder, build_placeholder_ranking_context, rank_common_placeholders, rank_recent_common_placeholders (weights 0.50/0.30/0.20, 14-day half-life, capped-lift relation with shrinkage, CommonPlaceholderIndex._ranking_memo). prompt_context_tokens is public so ranking and recording share one tokenizer. tests/history/test_prompt_placeholder_ranking.py covers the plan cases. just lint green. just check-full: 31880 passed, 11 skipped; one failure tests/test_config_cache.py::test_drain_config_token_refresh_joins_worker_and_advances_epoch reproduced isolated as pass (1.28s) and recorded as PROPOSED FOLLOW-UP. Justfile --epic-symbol entries for the four o8.3 APIs; load_common_placeholder_index retargeted from closed sase-o8.2 to sase-o8.4.

## Dependencies

- **Depends on:** [sase-o8.2](sase-o8.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o8.4](sase-o8.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-o8.3.md) | [sase-o8.3](sase-o8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`577986a`](https://github.com/sase-org/sase/commit/577986af5e33db57346e8c622845ed14e7c03b03) | feat(history): rank common placeholders by relation, recency, and frequency | [sase-o8.3](sase-o8.3.md) | 2026-08-17 07:46:19 EDT |
