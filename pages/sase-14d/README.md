# Bead: sase-14d — Client-side notification delivery rules

[Bead Pages](../README.md) / sase-14d

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.land`
**Created:** 2026-09-20 13:11:29 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/notification_delivery_rules.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md

<!-- sase:links:end -->

## Description

A person receiving SASE notifications can match them by tab, sender, action, tag, title, or note text, and decide per match whether a TUI toast is shown and whether the announcement is the terminal bell, a custom sound file, or silence. Task-bead notifications announce nothing on every machine, and kellys_mbp announces with a sound file instead of the bell.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-14d.1](sase-14d.1.md) | Rule matcher in the Rust core | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14d.2](sase-14d.2.md) | Config surface and Python facade | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14d.3](sase-14d.3.md) | Sound file playback | ✓ closed | small | 2026-09-20 | 1 | 1 |
| [sase-14d.4](sase-14d.4.md) | Apply rules in the notification poll | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14d.5](sase-14d.5.md) | sase notify rules, doctor check, and docs | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14d.6](sase-14d.6.md) | The two requested configurations | ✓ closed | small | 2026-09-20 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-14d: Client-side notification delivery rules [in_progress]"]
    n1["sase-14d.1: Rule matcher in the Rust core [closed]"]
    n2["sase-14d.2: Config surface and Python facade [closed]"]
    n3["sase-14d.3: Sound file playback [closed]"]
    n4["sase-14d.4: Apply rules in the notification poll [closed]"]
    n5["sase-14d.5: sase notify rules, doctor check, and docs [closed]"]
    n6["sase-14d.6: The two requested configurations [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n1 -.-> n4
    n2 -.-> n4
    n2 -.-> n5
    n2 -.-> n6
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.1/README.md) | [sase-14d.1](sase-14d.1.md) | 1 |
| [bbugyi200.athena.sase-14d.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.2/README.md) | [sase-14d.2](sase-14d.2.md) | 1 |
| [bbugyi200.athena.sase-14d.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.3/README.md) | [sase-14d.3](sase-14d.3.md) | 1 |
| [bbugyi200.athena.sase-14d.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.4/README.md) | [sase-14d.4](sase-14d.4.md) | 1 |
| [bbugyi200.athena.sase-14d.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.5/README.md) | [sase-14d.5](sase-14d.5.md) | 1 |
| [bbugyi200.athena.sase-14d.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.6/README.md) | [sase-14d.6](sase-14d.6.md) | 1 |
| [bbugyi200.athena.sase-14d.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.land/README.md) | [sase-14d](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1576385`](https://github.com/sase-org/sase/commit/15763853b338ad6e43b2610d4866e5aec67ec237) | feat(tui): add sound-file playback for notification delivery | [sase-14d.3](sase-14d.3.md) | 2026-09-20 13:28:57 EDT |
| sase-core | [`sase-core@a7f26b2`](https://github.com/sase-org/sase-core/commit/a7f26b2b2018901501c443931c518c86d5469110) | feat(notifications): add delivery rule matcher and resolve\_notification\_deliveries binding | [sase-14d.1](sase-14d.1.md) | 2026-09-20 13:31:24 EDT |
| sase | [`9a99238`](https://github.com/sase-org/sase/commit/9a99238cdf0e9e415575f5b11559cdb2f29c59c2) | feat(notifications): add ace.notification\_rules config and Python delivery facade | [sase-14d.2](sase-14d.2.md) | 2026-09-20 14:40:33 EDT |
| sase | [`0f5a81d`](https://github.com/sase-org/sase/commit/0f5a81da70e3fa4360d0f4eab1e44efdcfcb8ca9) | feat(tui): apply notification delivery rules in the poll | [sase-14d.4](sase-14d.4.md) | 2026-09-20 15:38:12 EDT |
| sase | [`03cc36b`](https://github.com/sase-org/sase/commit/03cc36be5c6ff17474f5390ed402bc82d3a53a5d) | feat(notify): add sase notify rules, doctor check, and delivery-rules docs | [sase-14d.5](sase-14d.5.md) | 2026-09-20 16:54:29 EDT |
| chezmoi | [`chezmoi@f7da682`](https://github.com/bbugyi200/dotfiles/commit/f7da68203d0b2d2568496fbac7f7c4497eb45870) | feat(sase): add notification delivery rules for task beads and kellys\_mbp chime | [sase-14d.6](sase-14d.6.md) | 2026-09-20 17:05:55 EDT |
