# Bead: sase-na — Rank Ctrl+T history words by relation, recency, and frequency

[Bead Pages](../README.md) / sase-na

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03s.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03s.w0.md) · **Assignee:** `sase-na.land`
**Created:** 2026-08-16 12:13:35 EDT
**Plan:** [202608/word\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/word_completion_ranking.md)

## Description

The Ctrl+T history-word menu ranks candidates by how strongly they relate to the words already in the prompt, how recently they were used, and how often they were used, and every row shows a compact, colored signal explaining why it ranks where it does.

## Notes

[2026-08-16T18:26:21Z · 044--1] DISCOVERED ISSUE: monitored just check-full z2awr5avszsa on master 71061cead and an exact isolated 'just _lint-symvision' reproduction both fail only because Justfile still names five temporary epic symbols under closed phase sase-na.2: RankedWord, WordRankingContext, build_word_ranking_context, rank_history_words, and rank_recent_history_words. Commit b0585490e introduced the scoring engine; active phase sase-na.3 explicitly owns wiring it into the warm cache and history-word menu, so that phase must retarget/remove the temporary exemptions as the production consumers land. This is unrelated to supervisor-owned proc epic sase-m9; no standalone task bead was created because active epic sase-na is the causal owner.

[2026-08-16T18:27:06Z · 044--1] DISCOVERED ISSUE: monitored just check-full z2awr5avszsa on master 71061cead and an exact isolated 'just _lint-symvision' reproduction both fail only because Justfile still names five temporary epic symbols under closed phase sase-na.2: RankedWord, WordRankingContext, build_word_ranking_context, rank_history_words, and rank_recent_history_words. Commit b0585490e introduced the scoring engine; active phase sase-na.3 explicitly owns wiring it into the warm cache and history-word menu, so that phase must retarget/remove the temporary exemptions as the production consumers land. This is unrelated to supervisor-owned proc epic sase-m9; no standalone task bead was created because active epic sase-na is the causal owner.

[2026-08-16T18:35:24Z · sase-m9.land] DISCOVERED ISSUE: Independently reproduced by sase-m9.land in workspace sase_12 on master 71061cead, corroborating the two 044--1 notes above. The blast radius is wider than check-full: plain 'just check' also fails, so every agent in every workspace is blocked from the mandatory pre-reply gate regardless of diff. My diff touches only src/sase/monitor/store.py and tests/monitor/test_monitor_store_reconcile.py; the run passed fmt (python), fmt (markdown), keep-sorted, ruff, mypy, feature-flag schema, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed lint (symvision) with the same five 'bead sase-na.2 is closed' errors for RankedWord, WordRankingContext, build_word_ranking_context, rank_history_words, and rank_recent_history_words (Justfile lines 334-338). Running phase sase-na.3 owns retargeting them at its production consumers. Recorded here rather than as a task bead because active epic sase-na is the causal owner.

[2026-08-16T19:13:49Z · sase-n8.6] DISCOVERED ISSUE (fourth independent reproduction, while implementing unrelated plan launch_control_alias_history_panel.md): 'just _lint-symvision' still fails on master (a892dce3a, verified via git stash) with the same five closed-bead sase-na.2 stale --epic-symbol entries already reported above (RankedWord, WordRankingContext, build_word_ranking_context, rank_history_words, rank_recent_history_words). Corroborating the 044--1 and sase-m9.land notes above — recording here rather than filing a task bead per those notes' guidance that active phase sase-na.3 is the causal owner and must retarget/remove the temporary exemptions as its production consumers land.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-na.1](sase-na.1.md) | Prompt-word corpus index | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-na.2](sase-na.2.md) | Relation, recency, and frequency scoring | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-na.3](sase-na.3.md) | Warm cache, menu, and settings wiring | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-na.4](sase-na.4.md) | Ranking signals in the completion panel | ◐ in_progress | medium | 2026-08-16 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-na: Rank Ctrl+T history words by relation, recency, and frequency [in_progress]"]
    n1["sase-na.1: Prompt-word corpus index [closed]"]
    n2["sase-na.2: Relation, recency, and frequency scoring [closed]"]
    n3["sase-na.3: Warm cache, menu, and settings wiring [closed]"]
    n4["sase-na.4: Ranking signals in the completion panel [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-na.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-na.1.md) | [sase-na.1](sase-na.1.md) | 1 |
| [bbugyi200.athena.sase-na.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.2/README.md) | [sase-na.2](sase-na.2.md) | 1 |
| [bbugyi200.athena.sase-na.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.3/README.md) | [sase-na.3](sase-na.3.md) | 1 |
| [bbugyi200.athena.sase-na.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.4/README.md) | [sase-na.4](sase-na.4.md) | 0 |
| [bbugyi200.athena.sase-na.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.land/README.md) | [sase-na](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed39dd0`](https://github.com/sase-org/sase/commit/ed39dd0b886b7dcccd96a859aa856913b430787a) | feat: add prompt-word history index | [sase-na.1](sase-na.1.md) | 2026-08-16 13:21:31 EDT |
| sase | [`b058549`](https://github.com/sase-org/sase/commit/b0585490e2457e0ee78c7eee9ed9d5d4ae7b5450) | feat(history): add prompt word ranking engine | [sase-na.2](sase-na.2.md) | 2026-08-16 14:10:17 EDT |
| sase | [`101af72`](https://github.com/sase-org/sase/commit/101af72428a1fc4f3c3c51f8cc25c57900c0adcb) | feat(history): wire ranked word completion into the history-word menu | [sase-na.3](sase-na.3.md) | 2026-08-16 15:20:00 EDT |
