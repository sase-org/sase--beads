# Bead: sase-19i.7.3.3.3.3 — Pass the Node Finder open p95 budget

[Bead Pages](../README.md) / [sase-19i.7.3.3.3](sase-19i.7.3.3.3.md) / sase-19i.7.3.3.3.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.3.land`
**Created:** 2026-09-26 18:21:12 EDT
**Plan:** [202609/node\_finder\_open\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_budget.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/node_finder_open_budget.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_budget.md

<!-- sase:links:end -->

## Description

The unchanged 2,000-node Node Finder open benchmark stays under 50 ms p95, with the other approved budgets still green and navigation unchanged.

## Notes

[2026-09-27T01:54:43Z · sase-1au.6.land] DISCOVERED ISSUE: proposed by sase-1au.6.1 note #1 and sase-1au.6.3 note #1, reproduced at master b9f53067b1 during the sase-1au.6 landing. .venv/bin/mypy src/sase/ace/tui/models/agent_groups/_tree.py reports three errors in build_agent_tree: line 622 name "prefix_key" already defined on line 411 [no-redef]; lines 623 and 629 [arg-type] because the line 411 binding infers tuple[tuple[str, str] | tuple[str], str, str] rather than GroupKey tuple[str, ...]. Commit 215eb89f41 (phase sase-19i.7.3.3.3.3.1) added that line 411 assignment and reused the name the later GroupKey annotation already used. Not Prompts-overlay work; no separate task.

[2026-09-27T06:13:13Z · sase-1aq.10.7.5.land] Corroboration (sase-1aq.10.7.5.land, 2026-09-27): the three build_agent_tree mypy errors (_tree.py:622 prefix_key no-redef, :623/:629 arg-type) from 215eb89f41 are still red at master 19abe261d4 (ToolRun 109aa65ee68b1d6365d33d297620dfab), also proposed by sase-1aq.10.7.5.1 note #1.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.3.land/README.md) | [sase-19i.7.3.3.3.3](sase-19i.7.3.3.3.3.md) | 0 |
