# Bead: sase-1eu — Three-pane splits for the Agents deck and the pager

[Bead Pages](../README.md) / sase-1eu

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.land`
**Created:** 2026-10-02 11:33:49 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

The Agents-tab deck and the sase pager share one closed split model with seven geometries: single, two two-pane splits, and four three-pane T shapes. The existing `\` / `|` keys follow one rule: erase a full-span divider, draw one through the focused pane, or turn a three-pane layout. New keys add a focus ring (`ctrl+f` / `ctrl+b`), content swap (`ctrl+shift+f` / `ctrl+shift+b`, aliases `>` / `<`), close-focused (`ctrl+shift+d`, alias `ctrl+x`) and turn (`ctrl+t`). Rendering is spatially stable, shows exactly one full-strength frame, and never remounts a pane. The work lands without colliding with the sase-1es pager performance epic.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1eu.1](sase-1eu.1.md) | Deliver the ctrl+shift chords through kitty and tmux | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1eu.2](sase-1eu.2.md) | Shared pure PaneGrid model and golden transition table | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.3](sase-1eu.3.md) | Agents deck on PaneGrid with flat grid rendering | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.4](sase-1eu.4.md) | Agents deck reverse focus, swap, close, and turn keys | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.5](sase-1eu.5.md) | Agents deck three panels behind the three\_pane\_splits beta flag | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.6](sase-1eu.6.md) | Pager on PaneGrid with grid panes and the new pane keys | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.7](sase-1eu.7.md) | Pager three panes with MRU ctrl+w and a target preview | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1eu.8](sase-1eu.8.md) | Remove the flag and finish docs, help, glossary, and release note | ◐ in_progress | small | 2026-10-02 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1eu: Three-pane splits for the Agents deck and the pager [in_progress]"]
    n1["sase-1eu.1: Deliver the ctrl+shift chords through kitty and tmux [closed]"]
    n2["sase-1eu.2: Shared pure PaneGrid model and golden transition table [in_progress]"]
    n3["sase-1eu.3: Agents deck on PaneGrid with flat grid rendering [in_progress]"]
    n4["sase-1eu.4: Agents deck reverse focus, swap, close, and turn keys [in_progress]"]
    n5["sase-1eu.5: Agents deck three panels behind the three_pane_splits beta flag [in_progress]"]
    n6["sase-1eu.6: Pager on PaneGrid with grid panes and the new pane keys [in_progress]"]
    n7["sase-1eu.7: Pager three panes with MRU ctrl+w and a target preview [in_progress]"]
    n8["sase-1eu.8: Remove the flag and finish docs, help, glossary, and release note [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n7
    n5 -.-> n8
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.1/README.md) | [sase-1eu.1](sase-1eu.1.md) | 1 |
| [bbugyi200.athena.sase-1eu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.2/README.md) | [sase-1eu.2](sase-1eu.2.md) | 0 |
| [bbugyi200.athena.sase-1eu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.3/README.md) | [sase-1eu.3](sase-1eu.3.md) | 0 |
| [bbugyi200.athena.sase-1eu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.4/README.md) | [sase-1eu.4](sase-1eu.4.md) | 0 |
| [bbugyi200.athena.sase-1eu.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.5/README.md) | [sase-1eu.5](sase-1eu.5.md) | 0 |
| [bbugyi200.athena.sase-1eu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.6/README.md) | [sase-1eu.6](sase-1eu.6.md) | 0 |
| [bbugyi200.athena.sase-1eu.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.7/README.md) | [sase-1eu.7](sase-1eu.7.md) | 0 |
| [bbugyi200.athena.sase-1eu.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.8/README.md) | [sase-1eu.8](sase-1eu.8.md) | 0 |
| [bbugyi200.athena.sase-1eu.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.land/README.md) | [sase-1eu](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@78f0db4`](https://github.com/bbugyi200/dotfiles/commit/78f0db4e04b069e211c0c4f93c5780c7e4a2d64f) | feat(terminal): pass ctrl+shift chords through kitty and tmux | [sase-1eu.1](sase-1eu.1.md) | 2026-10-02 11:53:45 EDT |
