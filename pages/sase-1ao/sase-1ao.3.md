# Bead: sase-1ao.3 — Remove adjacent model directives on shortcut acceptance

[Bead Pages](../README.md) / [sase-1ao](README.md) / sase-1ao.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1ao.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ao.land.md) · **Assignee:** `sase-1ao.3.land`
**Created:** 2026-09-26 13:15:19 EDT · **Closed:** 2026-09-26 15:46:15 EDT
**Plan:** [202609/model\_shortcut\_adjacent\_directives.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_adjacent_directives.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/model_shortcut_adjacent_directives.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_adjacent_directives.md

<!-- sase:links:end -->

## Description

Accepting =alias or ==model leaves exactly one standalone model directive in the active prompt segment, even when redundant directives are adjacent at a line boundary.

## Notes

[2026-09-26T19:46:15Z · sase-1ao.3.land] Verified phase sase-1ao.3.1 in source and tests. The shared planner now shrinks overlapping whitespace so accepting =alias or ==model removes every later standalone directive in the active segment, including adjacent ones, while alternation branches stay protected and edits stay pairwise disjoint. That repair is core 104d902 (rebased from unpublished 041f53b onto receipts commit 0cf5147 and pushed). Rust model_alias_shortcut tests: 32 passed. LSP adjacent tests: 2 passed. PyO3 segment-replacement binding passed. sase-core-revision.txt now pins e44af7d, which contains 104d902 plus the later prompt-stash commit (no shortcut overlap). Installed that core; focused ACE/LSP/widget tests passed 146, including adjacent accept and single undo. Commits since the epic started (beads reasons, card-blocks, gate turn, node-finder, shell-to-turn docs) do not touch shortcut code. Follow-ups: clippy denies match ready task sase-1an and received +1; flag-lint follow-up declined because check_feature_flags exits 0 (card_blocks gone with sase-1ad closed, legacy_sase_shell_syntax defined while sase-1ar remains the retirement). just check a4c074f6 passed through patch/stitch terminology and failed only on stale --epic-symbol sase-19i.7.3.3.2(describe_node_finder_row_from_facts); recorded as DISCOVERED ISSUE on in-progress epic sase-19i.7.3.3. sase-1ao.3 has no epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ao.3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ao.3.land/README.md) | [sase-1ao.3](sase-1ao.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`00f4975`](https://github.com/sase-org/sase/commit/00f4975d9c7236fb6eccf78cb1dc183769007955) | fix(core): pin the published adjacent model-directive cleanup | [sase-1ao.3](sase-1ao.3.md) | 2026-09-26 15:50:22 EDT |
