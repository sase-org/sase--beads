# Bead: sase-j3 — Snippet target mode for a single prompt input pane

[Bead Pages](../README.md) / sase-j3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xl/README.md) · **Assignee:** `sase-j3.land`
**Created:** 2026-08-10 14:49:25 EDT
**Plan:** [202608/snippet\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/snippet_target_mode.md)

## Description

Authoring and editing an ACE snippet is a first-class prompt-bar loop: `gt` / `Ctrl+G t` asks for the trigger name with live collision evidence, opens one visibly distinct snippet pane at the bottom of the prompt input stack (pre-filled with the existing definition when the trigger already exists), and `<enter>` saves it to the user's configured snippet config file — showing a real diff before writing and offering exactly the follow-up actions that file needs — after which the pane disappears and the cursor returns to precisely where it was.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-j3.1](sase-j3.1.md) | Snippet destination resolution, the new config field, and the collision index | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-j3.2](sase-j3.2.md) | Snippet panes in the prompt stack model | ✓ closed | medium | 2026-08-10 | 1 | 2 |
| [sase-j3.3](sase-j3.3.md) | Trigger-name panel with live collision evidence | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-j3.4](sase-j3.4.md) | The gt keymap, pane lifecycle, and exact cursor restoration | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-j3.5](sase-j3.5.md) | Save confirmation with a real diff, the write, and follow-up actions | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-j3.6](sase-j3.6.md) | Visual language for the snippet pane | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-j3.7](sase-j3.7.md) | Help modal and documentation | ✓ closed | small | 2026-08-10 | 1 | 1 |
| [sase-j3.8](sase-j3.8.md) | End-to-end verification of the snippet loop | ◐ in_progress | small | 2026-08-10 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-j3: Snippet target mode for a single prompt input pane [in_progress]"]
    n1["sase-j3.1: Snippet destination resolution, the new config field, and the collision index [closed]"]
    n2["sase-j3.2: Snippet panes in the prompt stack model [closed]"]
    n3["sase-j3.3: Trigger-name panel with live collision evidence [closed]"]
    n4["sase-j3.4: The gt keymap, pane lifecycle, and exact cursor restoration [closed]"]
    n5["sase-j3.5: Save confirmation with a real diff, the write, and follow-up actions [closed]"]
    n6["sase-j3.6: Visual language for the snippet pane [closed]"]
    n7["sase-j3.7: Help modal and documentation [closed]"]
    n8["sase-j3.8: End-to-end verification of the snippet loop [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
    n3 -.-> n7
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.1/README.md) | [sase-j3.1](sase-j3.1.md) | 1 |
| [bbugyi200.athena.sase-j3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.2/README.md) | [sase-j3.2](sase-j3.2.md) | 2 |
| [bbugyi200.athena.sase-j3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.3/README.md) | [sase-j3.3](sase-j3.3.md) | 1 |
| [bbugyi200.athena.sase-j3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.4/README.md) | [sase-j3.4](sase-j3.4.md) | 1 |
| [bbugyi200.athena.sase-j3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.5/README.md) | [sase-j3.5](sase-j3.5.md) | 1 |
| [bbugyi200.athena.sase-j3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.6/README.md) | [sase-j3.6](sase-j3.6.md) | 1 |
| [bbugyi200.athena.sase-j3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.7/README.md) | [sase-j3.7](sase-j3.7.md) | 1 |
| [bbugyi200.athena.sase-j3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.8/README.md) | [sase-j3.8](sase-j3.8.md) | 0 |
| [bbugyi200.athena.sase-j3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.land/README.md) | [sase-j3](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e015840`](https://github.com/sase-org/sase/commit/e01584098b773fd177331e923d346ec981040113) | feat(ace): add snippet destination resolver, config field, and collision index | [sase-j3.1](sase-j3.1.md) | 2026-08-10 15:28:16 EDT |
| sase | [`4d8be52`](https://github.com/sase-org/sase/commit/4d8be52cf1821d435c87ffc442fc87dd05cc3088) | feat(ace): add prompt stack snippet pane model | [sase-j3.2](sase-j3.2.md) | 2026-08-10 15:47:24 EDT |
| sase | [`21c8321`](https://github.com/sase-org/sase/commit/21c83218fe1a7c8fc81c440ab09bde90d5ebbe82) | fix(ace): keep snippet pane target internal | [sase-j3.2](sase-j3.2.md) | 2026-08-10 15:59:33 EDT |
| sase | [`64ddea9`](https://github.com/sase-org/sase/commit/64ddea98a879ef774c41fc2bc10b7ccc6c101a55) | feat(tui): add snippet trigger name modal | [sase-j3.3](sase-j3.3.md) | 2026-08-10 16:20:08 EDT |
| sase | [`ba77762`](https://github.com/sase-org/sase/commit/ba77762e68fd045df73b8106dd589d91787e9ca1) | feat(ace): add snippet target pane lifecycle | [sase-j3.4](sase-j3.4.md) | 2026-08-10 17:01:58 EDT |
| sase | [`de530b3`](https://github.com/sase-org/sase/commit/de530b340f6bbd1dd14ccb7f00f122cd145aa99f) | feat(ace): confirm snippet pane saves | [sase-j3.5](sase-j3.5.md) | 2026-08-10 17:45:58 EDT |
| sase | [`0ccd7f8`](https://github.com/sase-org/sase/commit/0ccd7f84473191551aba0091b8ca9c401053d579) | feat(ace): give the snippet pane its own theme-safe visual language | [sase-j3.6](sase-j3.6.md) | 2026-08-10 17:53:29 EDT |
| sase | [`aae179e`](https://github.com/sase-org/sase/commit/aae179e86fabbffdf3e572b808d531884e317564) | docs(ace): document snippet pane keybinding and config field | [sase-j3.7](sase-j3.7.md) | 2026-08-10 18:07:03 EDT |
