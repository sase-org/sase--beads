# Bead: sase-na.2 — Relation, recency, and frequency scoring

[Bead Pages](../README.md) / [sase-na](README.md) / sase-na.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03s.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03s.w0.md) · **Assignee:** `sase-na.2` · **Size:** medium
**Created:** 2026-08-16 12:14:18 EDT · **Closed:** 2026-08-16 14:05:45 EDT
**Plan:** [202608/word\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/word_completion_ranking.md)

## Description

ranking: add the pure scoring engine that turns the corpus index plus the current prompt text into ranked words with per-signal contributions, a dominant reason, and the evidence each row displays.

## Notes

[2026-08-16T18:02:41Z · sase-na.2] PROPOSED FOLLOW-UP: unrelated full-suite verification failures reproduced directly — tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs sees schema_version 22 vs Python constant 21, and tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] outputs an extra Flags: 0 line; config-cache failure from the full-suite run passed direct rerun.

[2026-08-16T18:05:45Z · sase-na.2] Implemented src/sase/history/prompt_word_ranking.py with relation/recency/frequency scoring, memoized prompt relation contexts, smart prefix ranking, MRU recent-mode ranking, ranked row evidence, and tests/history/test_prompt_word_ranking.py behavior coverage. Verified .venv/bin/pytest tests/history/test_prompt_word_ranking.py (11 passed, 1 slow deselected), just _lint-symvision, just _lint-mypy, Ruff check, and Ruff format check. just check ran through lint/SASE validation and escalated to full suite because Justfile gained temporary Symvision epic-symbol entries; it failed only unrelated reproduced tests noted as a PROPOSED FOLLOW-UP on this bead.

[2026-08-16T18:08:24Z · sase-na.2] Verified focused ranking tests, Symvision, mypy, Ruff check, and format check; full just check reached unrelated reproduced failures recorded as proposed follow-up.

## Dependencies

- **Depends on:** [sase-na.1](sase-na.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-na.3](sase-na.3.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-na.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.2/README.md) | [sase-na.2](sase-na.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b058549`](https://github.com/sase-org/sase/commit/b0585490e2457e0ee78c7eee9ed9d5d4ae7b5450) | feat(history): add prompt word ranking engine | [sase-na.2](sase-na.2.md) | 2026-08-16 14:10:17 EDT |
