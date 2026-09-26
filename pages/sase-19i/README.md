# Bead: sase-19i — Agents-tab Node Finder on the " key

[Bead Pages](../README.md) / sase-19i

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s5.md) · **Assignee:** `sase-19i.land`
**Created:** 2026-09-25 13:06:05 EDT
**Plan:** [202609/agents\_node\_finder.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_finder.md)

## Description

Pressing `"` on the Agents tab opens a large Node Finder modal. It lists every reachable sase node as a tree, including nodes hidden by folds, collapsed grouping banners, collapsed or isolated tribe panels, the Agents query, and (last phase) the `I` hide-non-run toggle. Every jumpable row always carries a jump hint. A query bar that starts unfocused (Tab toggles it) fuzzy-filters by node name. Enter and Ctrl+N/Ctrl+P navigate. A fast two-tier preview shows the highlighted node. Every jump lands reliably through the existing identity-based reveal primitive, and every change it makes to view state is announced and can be undone.

## Notes

[2026-09-26T00:48:18Z · sase-17x.13.10.land] DISCOVERED ISSUE (sase-17x.13.10 land agent, master 7cb835953): d62a459a2 (sase-19i.3, Node Finder previews) added a marker path-passing site that the audit has not reviewed: tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed fails deterministically on a clean tree with 'Extra items in the left set: src/sase/ace/tui/modals/node_finder_preview_loader.py:_source_paths'. Review the site and add it to _REVIEWED_PATH_PASSING_CONTEXTS (or stop passing the marker path).

[2026-09-26T01:12:14Z · sase-17m.land] DISCOVERED ISSUE corroboration (sase-17m land agent, 2026-09-25, master eba6b80d0): an independent reproduction of note #1 under sase tool run check (ToolRun 7263b9ee3f7bc48d3764693f0b934ba6) and again on a clean stashed tree: tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed still fails with the extra unreviewed site src/sase/ace/tui/modals/node_finder_preview_loader.py:_source_paths (from d62a459a2, sase-19i.3).

[2026-09-26T01:13:18Z · sase-17x.13.10.land] Update from the sase-17x.13.10 land agent: the marker path-passing audit failure (node_finder_preview_loader.py:_source_paths) still reproduces on origin/master 013a17072; the audit's reviewed list does not name the loader.

[2026-09-26T10:01:44Z · sase-19i.land] LAND REVIEW 2026-09-26: Six phases closed. Marker-path audit note #1-3 now addressed at tests/test_agent_artifact_marker_path_passing_audit.py:_source_paths; targeted audit 2/2 passed. No sase-19i epic-symbol entries remain. Later CardBlock/Agent Session Reply changes do not alter the Node Finder's plain-text modal preview; queue/session and Symvision clean-base reports from phase notes have subsequent fixes. Performance remains epic work: current 2,000-node bench open p50 166.50ms/p95 436.58ms vs <50ms, highlight p95 19.49ms vs <16ms; narrow keystroke p95 0.40ms passes, while phase .5 also reports ~190ms broad-query refilter. A child epic plan is being proposed for these remaining performance paths. Original PROPOSED FOLLOW-UP notes still require final noncausal triage in the resumed land review after child landing.

[2026-09-26T14:23:32Z · sase-19i.7.land] DISCOVERED ISSUE: during sase-19i.7 land review at 7cdde2b32, targeted visual run .venv/bin/pytest -q -m visual tests/ace/tui/visual/test_ace_png_snapshots_agents_node_finder.py failed 5/7 Node Finder PNG nodes (hints, search, pending-prefix, query-hidden, I-hidden; narrow and no-results passed). Phase sase-19i.7.2 PROPOSED FOLLOW-UP #3 reports the same five failures on its clean pre-phase base, so this predates that child performance work and belongs to this still-open Node Finder epic. Inspect generated diff artifacts and either correct actual rendering or intentionally update inspected goldens before parent landing; do not treat child performance budget completion as visual approval.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-19i.1](sase-19i.1.md) | Node Finder row model, snapshot, filtering, and hints | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.2](sase-19i.2.md) | Identity jump ladder with an announced query clear | ✓ closed | small | 2026-09-25 | 1 | 1 |
| [sase-19i.3](sase-19i.3.md) | Two-tier Node Finder preview | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.4](sase-19i.4.md) | NodeFinderModal screen, modes, keys, and layout | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.5](sase-19i.5.md) | Keymap, action, docs, visual goldens, and bench | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.6](sase-19i.6.md) | Rows hidden by I, with a flip-and-reveal rung | ✓ closed | medium | 2026-09-25 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-19i: Agents-tab Node Finder on the \" key [in_progress]"]
    n1["sase-19i.1: Node Finder row model, snapshot, filtering, and hints [closed]"]
    n2["sase-19i.2: Identity jump ladder with an announced query clear [closed]"]
    n3["sase-19i.3: Two-tier Node Finder preview [closed]"]
    n4["sase-19i.4: NodeFinderModal screen, modes, keys, and layout [closed]"]
    n5["sase-19i.5: Keymap, action, docs, visual goldens, and bench [closed]"]
    n6["sase-19i.6: Rows hidden by I, with a flip-and-reveal rung [closed]"]
    n7["sase-19i.7: Finish Node Finder performance budgets [in_progress]"]
    n8["sase-19i.7.1: Bound snapshot and broad-query filter work [closed]"]
    n9["sase-19i.7.2: Meet first-paint, broad-query, and highlight budgets [closed]"]
    n10["sase-19i.7.3: Finish the remaining Node Finder open and broad-query budgets [in_progress]"]
    n11["sase-19i.7.3.1: Bound snapshot construction for first paint [closed]"]
    n12["sase-19i.7.3.2: Finish open and broad-query p95 budgets [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n7 --> n8
    n7 --> n9
    n7 --> n10
    n10 --> n11
    n10 --> n12
    n1 -.-> n3
    n1 -.-> n4
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n8 -.-> n9
    n11 -.-> n12
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.1/README.md) | [sase-19i.1](sase-19i.1.md) | 1 |
| [bbugyi200.athena.sase-19i.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.2.md) | [sase-19i.2](sase-19i.2.md) | 1 |
| [bbugyi200.athena.sase-19i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.3/README.md) | [sase-19i.3](sase-19i.3.md) | 1 |
| [bbugyi200.athena.sase-19i.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.4.md) | [sase-19i.4](sase-19i.4.md) | 1 |
| [bbugyi200.athena.sase-19i.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.5.md) | [sase-19i.5](sase-19i.5.md) | 1 |
| [bbugyi200.athena.sase-19i.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.6.md) | [sase-19i.6](sase-19i.6.md) | 1 |
| [bbugyi200.athena.sase-19i.7.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.1.md) | [sase-19i.7.1](sase-19i.7.1.md) | 1 |
| [bbugyi200.athena.sase-19i.7.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.2.md) | [sase-19i.7.2](sase-19i.7.2.md) | 1 |
| [bbugyi200.athena.sase-19i.7.3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.1/README.md) | [sase-19i.7.3.1](sase-19i.7.3.1.md) | 1 |
| [bbugyi200.athena.sase-19i.7.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.2/README.md) | [sase-19i.7.3.2](sase-19i.7.3.2.md) | 1 |
| [bbugyi200.athena.sase-19i.7.3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.land/README.md) | [sase-19i.7.3](sase-19i.7.3.md) | 0 |
| [bbugyi200.athena.sase-19i.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.land.md) | [sase-19i.7](sase-19i.7.md) | 0 |
| [bbugyi200.athena.sase-19i.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.land.md) | [sase-19i](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee22eb3`](https://github.com/sase-org/sase/commit/ee22eb305c7c19eb960a1569286025d5434efe27) | feat(node-finder): add row model, snapshot, filtering, and hints (sase-19i.1) | [sase-19i.1](sase-19i.1.md) | 2026-09-25 16:24:33 EDT |
| sase | [`0854519`](https://github.com/sase-org/sase/commit/085451924eaedf9c882d1a8e0f0ab4b64b74b5e9) | feat(ace): add node identity jump ladder | [sase-19i.2](sase-19i.2.md) | 2026-09-25 16:37:18 EDT |
| sase | [`d62a459`](https://github.com/sase-org/sase/commit/d62a459a2d527d663cfd425104add367acee4f7e) | feat(tui): add Node Finder previews | [sase-19i.3](sase-19i.3.md) | 2026-09-25 17:17:23 EDT |
| sase | [`89ebc76`](https://github.com/sase-org/sase/commit/89ebc76256aeefdb28c1e1acfc05469ecfe32cb6) | feat(ace): add the Agents-tab Node Finder modal | [sase-19i.4](sase-19i.4.md) | 2026-09-25 21:20:40 EDT |
| sase | [`df0d58d`](https://github.com/sase-org/sase/commit/df0d58d337f06b8e20878ebc0734a6309041c647) | feat(agents-finder): wire quotation\_mark to jump\_to\_node with goldens and bench | [sase-19i.5](sase-19i.5.md) | 2026-09-25 23:45:37 EDT |
| sase | [`aa5fc55`](https://github.com/sase-org/sase/commit/aa5fc5503b05cea27667575a010889d65d1608ff) | feat(ace): add hidden node finder reveal coverage | [sase-19i.6](sase-19i.6.md) | 2026-09-26 00:17:16 EDT |
| sase | [`f62604e`](https://github.com/sase-org/sase/commit/f62604e712dde4092da845f3c5edce6023f1da96) | perf(node-finder): bound snapshot and broad-query filter work (sase-19i.7.1) | [sase-19i.7.1](sase-19i.7.1.md) | 2026-09-26 06:40:00 EDT |
| sase | [`0b55415`](https://github.com/sase-org/sase/commit/0b55415cd7e5178fc966b85c718ac5a7b015f8d4) | feat(ace): add agent node finder modal with snapshot, preview and fuzzy model | [sase-19i.7.2](sase-19i.7.2.md) | 2026-09-26 10:10:45 EDT |
| sase | [`d1b72cf`](https://github.com/sase-org/sase/commit/d1b72cfe58e815deafe4e7c72c4774b487346efd) | feat(ace): fuse per-open Node Finder snapshot facets (sase-19i.7.3.1) | [sase-19i.7.3.1](sase-19i.7.3.1.md) | 2026-09-26 10:49:28 EDT |
| sase | [`221d72a`](https://github.com/sase-org/sase/commit/221d72a13125e1e967305e0c79b5ab9d38b8c653) | perf(tui): exact-semantics node-finder snapshot optimizations | [sase-19i.7.3.2](sase-19i.7.3.2.md) | 2026-09-26 12:04:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.land][1] | Check whether active epic owns clean-HEAD test failures found while landing sase-17m | 1 |
| read-by | [agent:sase-17x.13.10.land][2] | Avoid duplicating DISCOVERED ISSUE notes | 2 |
| read-by | [agent:sase-19p.4.land][3] | Need follow-up bead status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19p.4.land/README.md

<!-- sase:referenced-by:end -->
