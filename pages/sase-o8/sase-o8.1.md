# Bead: sase-o8.1 — Shared ranking-signal rendering

[Bead Pages](../README.md) / [sase-o8](README.md) / sase-o8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.1` · **Size:** small
**Created:** 2026-08-17 06:01:52 EDT · **Closed:** 2026-08-17 06:32:30 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

signals_core: extract the score meter, dominant-reason chip, age formatter, palette, and colored legend out of the history-word row module into a provider-neutral rendering module behind a structural signal protocol, leaving history-word output byte-identical.

## Notes

[2026-08-17T10:32:30Z · sase-o8.1] Extracted score meter, reason chip, age formatter, palette, and colored legend from _history_word_rows.py into provider-neutral _ranking_signal_rows.py behind a structural _RankingSignals protocol; history-word output is byte-identical (test_history_word_rows.py assertions unchanged in behavior). just check passed clean: all lint gates green (fmt, ruff, mypy, symvision, etc.) and scoped test suite (129 files, includes new test_ranking_signal_rows.py and slimmed test_history_word_rows.py) passed. Fixed a pre-existing arithmetic bug in a new test assertion (13 vs 14 expected cells) and made RankingSignals private (_RankingSignals) per symvision's single-file-usage rule.

## Dependencies

- **Blocks:** [sase-o8.5](sase-o8.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.1/README.md) | [sase-o8.1](sase-o8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`555eba0`](https://github.com/sase-org/sase/commit/555eba0b13d7392912e34567180c057a79c936e0) | refactor(ace-tui): extract shared ranking-signal rendering | [sase-o8.1](sase-o8.1.md) | 2026-08-17 06:33:12 EDT |
