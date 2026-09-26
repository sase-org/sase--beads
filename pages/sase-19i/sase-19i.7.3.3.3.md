# Bead: sase-19i.7.3.3.3 — Finish Node Finder open and broad-query budgets

[Bead Pages](../README.md) / [sase-19i.7.3.3](sase-19i.7.3.3.md) / sase-19i.7.3.3.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.land`
**Created:** 2026-09-26 15:55:43 EDT
**Plan:** [202609/node\_finder\_open\_and\_broad\_tail.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_and_broad_tail.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/node_finder_open_and_broad_tail.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_and_broad_tail.md

<!-- sase:links:end -->

## Description

The 2,000-node Node Finder passes the unchanged first-paint and refilter p95 budgets with exact navigation behavior.

## Notes

[2026-09-26T22:19:00Z · sase-19i.7.3.3.3.land] LAND REVIEW, pending child plan: both phase notes and commits 4be908bb66 and 0a74b4f25c are in the tree (facet tables, plain-row describer, keep-all fold skip, shared walk order, skipped banner indexes, filter_tree_rows all-match early-out, per-modal view memo, identical-rebuild skip). Official bench on acbd5999ad still fails open: p50 73.42ms p95 113.02ms max 427.48ms (budget <50). keystroke-dispatch p95 0.01, keystroke 0.96, broad 5.46, and highlight 0.55 pass. Open p50 is over 50, so this is the distribution, not one GC spike. That miss is remaining epic work and is planned as a nested child. Integration after 4be908bb66, excluding the epic stitches: 4e7262d675, 74c89a6385, e95241543d, f7886b1a64, and acbd5999ad do not edit the finder snapshot, modal, filter, or bench. Clan neighbors is prompt-panel and member-jump indexing; no finder caller needs retargeting. No --epic-symbol entries. Follow-ups: phase .1 #2 residual 1-2ms cuts stay inside the child snapshot phase; phase .1 #3 / phase .2 collection ImportErrors still reproduce and are already on active sase-1ab notes #2 and #4 (corroborated again); phase .1 #4 memory drift is declined because sase init memory --check exits 0 on this tree; phase .2 #2 open miss is the child plan, not a separate task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.3.land.md) | [sase-19i.7.3.3.3](sase-19i.7.3.3.3.md) | 0 |
