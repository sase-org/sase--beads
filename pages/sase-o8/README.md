# Bead: sase-o8 — Rank saved placeholder tags by relation, recency, and frequency

[Bead Pages](../README.md) / sase-o8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.land`
**Created:** 2026-08-17 06:01:52 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

The `<` completion menu ranks saved placeholder tags by how strongly they relate to the prompt being written, how recently they were used, and how often they were used, and every saved row shows the same compact, colored signal the history-word menu already uses to explain its ordering.

## Notes

[2026-08-17T11:10:24Z · 04i] DISCOVERED ISSUE: Justfile's _lint-symvision recipe still carries --epic-symbol "sase-o8.2(CommonPlaceholderIndex)" and --epic-symbol "sase-o8.2(load_common_placeholder_index)" for phase sase-o8.2, which is now closed. Symvision correctly rejects these as stale ("bead 'sase-o8.2' is closed. Remove this stale --epic-symbol entry and clean up the symbol."), so 'just check'/'just lint' fail on a clean master for every agent until they're removed and CommonPlaceholderIndex/load_common_placeholder_index (src/sase/history/prompt_placeholders.py) are properly wired up, privatized, or pragma'd per sase/memory/symvision.md. Discovered while implementing the unrelated notification_modal_g_top_bottom plan; confirmed pre-existing via 'git stash' + running symvision directly on clean master (commit ded7f1a5f). This is a fresh instance of the exact recurring pattern tracked by open task sase-o7 (systemic fix: epic land should retire its own --epic-symbol entries at close time) — sase-o7 cites sase-o4's close note as the best worked example of the per-symbol resolution shape. Recommend the sase-o8 land agent remove these two entries and resolve the two symbols as part of landing this epic.

[2026-08-17T11:45:48Z · 04j] DISCOVERED ISSUE: independently reproduced the stale sase-o8.2 --epic-symbol lint failure while implementing grouping_cycle_back_to_o (unrelated tree). just check dies at lint (symvision) on Justfile lines for CommonPlaceholderIndex and load_common_placeholder_index because sase-o8.2 is closed. Corroborates 04i's earlier note on this epic and ready task sase-o7. Still recommend the sase-o8 land agent retire these two entries and resolve the two symbols as part of landing.

[2026-08-17T12:29:59Z · toobig-2x.split_file.tests.monitor.test_monitor_start.0] DISCOVERED ISSUE: just check's lint (symvision) gate is red on a tree with only tests/ changes (HEAD 7202e847b, diff = tests/monitor/*.py only, so unrelated to the reporting diff). Symvision rejects 5 Justfile _lint-symvision entries because their phase beads closed while this epic is still in progress: sase-o8.3(RankedPlaceholder), sase-o8.3(build_placeholder_ranking_context), sase-o8.3(rank_common_placeholders), sase-o8.3(rank_recent_common_placeholders) at Justfile:326-329, and sase-o8.4(load_common_placeholder_index) at Justfile:330. Error per entry: "bead 'sase-o8.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol." Reproduce: just install && just _lint-symvision. Impact: every agent whose tree reaches this gate is blocked by a whitelist unrelated to their diff, until sase-o8 finishes. Note this is the mid-epic variant of the known pattern: phases 3 and 4 closed while phase 5 (sase-o8.5) is still open, so the entries went stale before the land step. Suggested handling for the o8.5/land worker: re-key the still-needed entries to a bead that is still open (sase-o8 or sase-o8.5) or wire up/privatize the symbols now, and drop the entries at close.

[2026-08-17T12:41:02Z · 04l] DISCOVERED ISSUE: independently reproduced the stale sase-o8.3 / sase-o8.4 --epic-symbol lint failure while implementing monitor_node_under_starter (unrelated tree). just check dies at lint (symvision) on the five Justfile entries for RankedPlaceholder, build_placeholder_ranking_context, rank_common_placeholders, rank_recent_common_placeholders, and load_common_placeholder_index because phases o8.3 and o8.4 are closed. Corroborates the earlier DISCOVERED ISSUE notes. Still recommend the o8.5/land worker re-key still-needed entries to an open bead or resolve the symbols now.

[2026-08-17T12:49:56Z · 04o] DISCOVERED ISSUE: independently reproduced the stale sase-o8.4 --epic-symbol lint failure while implementing bead_work_family_member_bead_association (unrelated tree). just check dies at lint (symvision) on --epic-symbol 'sase-o8.4(PlaceholderRankingMetadata)' because phase sase-o8.4 is closed. Earlier notes on this epic named sase-o8.4(load_common_placeholder_index) and the o8.3 ranking symbols; this run surfaced PlaceholderRankingMetadata as the first rejected entry. Same recommended handling: o8.5/land worker should re-key still-needed entries to an open bead or resolve the symbols now. Pattern tracked by ready task sase-o7.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-o8.1](sase-o8.1.md) | Shared ranking-signal rendering | ✓ closed | small | 2026-08-17 | 1 | 1 |
| [sase-o8.2](sase-o8.2.md) | Placeholder context store | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-o8.3](sase-o8.3.md) | Relation, recency, and frequency scoring | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-o8.4](sase-o8.4.md) | Warm cache, menu, and settings wiring | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-o8.5](sase-o8.5.md) | Ranking signals in the placeholder panel | ✓ closed | medium | 2026-08-17 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-o8: Rank saved placeholder tags by relation, recency, and frequency [in_progress]"]
    n1["sase-o8.1: Shared ranking-signal rendering [closed]"]
    n2["sase-o8.2: Placeholder context store [closed]"]
    n3["sase-o8.3: Relation, recency, and frequency scoring [closed]"]
    n4["sase-o8.4: Warm cache, menu, and settings wiring [closed]"]
    n5["sase-o8.5: Ranking signals in the placeholder panel [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n5
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.1/README.md) | [sase-o8.1](sase-o8.1.md) | 1 |
| [bbugyi200.athena.sase-o8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.2/README.md) | [sase-o8.2](sase-o8.2.md) | 1 |
| [bbugyi200.athena.sase-o8.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-o8.3.md) | [sase-o8.3](sase-o8.3.md) | 1 |
| [bbugyi200.athena.sase-o8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.4/README.md) | [sase-o8.4](sase-o8.4.md) | 1 |
| [bbugyi200.athena.sase-o8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.5/README.md) | [sase-o8.5](sase-o8.5.md) | 1 |
| [bbugyi200.athena.sase-o8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.land/README.md) | [sase-o8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`555eba0`](https://github.com/sase-org/sase/commit/555eba0b13d7392912e34567180c057a79c936e0) | refactor(ace-tui): extract shared ranking-signal rendering | [sase-o8.1](sase-o8.1.md) | 2026-08-17 06:33:12 EDT |
| sase | [`ded7f1a`](https://github.com/sase-org/sase/commit/ded7f1a5f05e4d2c1554cd75677f874b7eac6b1f) | feat(history): persist placeholder context bags and corpus stats | [sase-o8.2](sase-o8.2.md) | 2026-08-17 06:58:24 EDT |
| sase | [`577986a`](https://github.com/sase-org/sase/commit/577986af5e33db57346e8c622845ed14e7c03b03) | feat(history): rank common placeholders by relation, recency, and frequency | [sase-o8.3](sase-o8.3.md) | 2026-08-17 07:46:19 EDT |
| sase | [`68aaa68`](https://github.com/sase-org/sase/commit/68aaa68634d2462af15fea43c10c9e8dc62a549c) | feat(ace-tui): rank saved placeholder tags from the warm cache | [sase-o8.4](sase-o8.4.md) | 2026-08-17 08:27:25 EDT |
| sase | [`5abf9eb`](https://github.com/sase-org/sase/commit/5abf9eb64e3cc85b50ccf5d91d77f78c4a83a767) | feat(ace-tui): render ranking evidence on placeholder completion rows | [sase-o8.5](sase-o8.5.md) | 2026-08-17 09:09:12 EDT |
