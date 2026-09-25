# Bead: sase-19i — Agents-tab Node Finder on the " key

[Bead Pages](../README.md) / sase-19i

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0s5.md) · **Assignee:** `sase-19i.land`
**Created:** 2026-09-25 13:06:05 EDT
**Plan:** [202609/agents\_node\_finder.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_finder.md)

## Description

Pressing `"` on the Agents tab opens a large Node Finder modal. It lists every reachable sase node as a tree, including nodes hidden by folds, collapsed grouping banners, collapsed or isolated tribe panels, the Agents query, and (last phase) the `I` hide-non-run toggle. Every jumpable row always carries a jump hint. A query bar that starts unfocused (Tab toggles it) fuzzy-filters by node name. Enter and Ctrl+N/Ctrl+P navigate. A fast two-tier preview shows the highlighted node. Every jump lands reliably through the existing identity-based reveal primitive, and every change it makes to view state is announced and can be undone.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-19i.1](sase-19i.1.md) | Node Finder row model, snapshot, filtering, and hints | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.2](sase-19i.2.md) | Identity jump ladder with an announced query clear | ✓ closed | small | 2026-09-25 | 1 | 1 |
| [sase-19i.3](sase-19i.3.md) | Two-tier Node Finder preview | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-19i.4](sase-19i.4.md) | NodeFinderModal screen, modes, keys, and layout | ◐ in_progress | medium | 2026-09-25 | 1 | 0 |
| [sase-19i.5](sase-19i.5.md) | Keymap, action, docs, visual goldens, and bench | ◐ in_progress | medium | 2026-09-25 | 1 | 0 |
| [sase-19i.6](sase-19i.6.md) | Rows hidden by I, with a flip-and-reveal rung | ◐ in_progress | medium | 2026-09-25 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-19i: Agents-tab Node Finder on the \" key [in_progress]"]
    n1["sase-19i.1: Node Finder row model, snapshot, filtering, and hints [closed]"]
    n2["sase-19i.2: Identity jump ladder with an announced query clear [closed]"]
    n3["sase-19i.3: Two-tier Node Finder preview [closed]"]
    n4["sase-19i.4: NodeFinderModal screen, modes, keys, and layout [in_progress]"]
    n5["sase-19i.5: Keymap, action, docs, visual goldens, and bench [in_progress]"]
    n6["sase-19i.6: Rows hidden by I, with a flip-and-reveal rung [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n3
    n1 -.-> n4
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.1/README.md) | [sase-19i.1](sase-19i.1.md) | 1 |
| [bbugyi200.athena.sase-19i.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.2.md) | [sase-19i.2](sase-19i.2.md) | 1 |
| [bbugyi200.athena.sase-19i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.3/README.md) | [sase-19i.3](sase-19i.3.md) | 1 |
| [bbugyi200.athena.sase-19i.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.4/README.md) | [sase-19i.4](sase-19i.4.md) | 0 |
| [bbugyi200.athena.sase-19i.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.5/README.md) | [sase-19i.5](sase-19i.5.md) | 0 |
| [bbugyi200.athena.sase-19i.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.6/README.md) | [sase-19i.6](sase-19i.6.md) | 0 |
| [bbugyi200.athena.sase-19i.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.land/README.md) | [sase-19i](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee22eb3`](https://github.com/sase-org/sase/commit/ee22eb305c7c19eb960a1569286025d5434efe27) | feat(node-finder): add row model, snapshot, filtering, and hints (sase-19i.1) | [sase-19i.1](sase-19i.1.md) | 2026-09-25 16:24:33 EDT |
| sase | [`0854519`](https://github.com/sase-org/sase/commit/085451924eaedf9c882d1a8e0f0ab4b64b74b5e9) | feat(ace): add node identity jump ladder | [sase-19i.2](sase-19i.2.md) | 2026-09-25 16:37:18 EDT |
| sase | [`d62a459`](https://github.com/sase-org/sase/commit/d62a459a2d527d663cfd425104add367acee4f7e) | feat(tui): add Node Finder previews | [sase-19i.3](sase-19i.3.md) | 2026-09-25 17:17:23 EDT |
