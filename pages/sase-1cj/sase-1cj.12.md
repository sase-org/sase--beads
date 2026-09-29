# Bead: sase-1cj.12 — Finish next-word prediction correctness, budgets, and calibration

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.12

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.land`
**Created:** 2026-09-29 18:29:13 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

## Description

The next-word prediction feature from epic sase-1cj meets its own contract. The core blocks every structural tail, including `%{...}` alternation. Support counts and confidence presets are honest and calibrated. Predict meets the p95 ≤ 0.5 ms local budget on real history. The TUI ghost never goes stale or inserts in the wrong place. The missing goldens, the archive default decision, and the epic-symbol cleanup are done, so sase-1cj can close.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.land/README.md) | [sase-1cj.12](sase-1cj.12.md) | 0 |
