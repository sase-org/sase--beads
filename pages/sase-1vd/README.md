# Bead: sase-1vd — Question copy panel

[Bead Pages](../README.md) / sase-1vd

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.land`
**Created:** 2026-11-26 10:49:27 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/question_copy_panel.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md

<!-- sase:links:end -->

## Description

From the questions gate, the user can copy any agent-declared snippet, the question text, the highlighted option, or the whole Q&A with two keypresses (`y` then one key), exactly byte-for-byte, with visible progress through multi-paste workflows. The same structured copy contract reaches Telegram and agent guidance.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1vd.1](sase-1vd.1.md) | Core copy contract and creation-time validation | ✓ closed | medium | 2026-11-26 | 1 | 2 |
| [sase-1vd.2](sase-1vd.2.md) | Generalize the Copy as palette | ✓ closed | medium | 2026-11-26 | 1 | 1 |
| [sase-1vd.3](sase-1vd.3.md) | Question copy panel behind y | ✓ closed | medium | 2026-11-26 | 1 | 1 |
| [sase-1vd.4](sase-1vd.4.md) | Discoverability cues on the question pane | ✓ closed | small | 2026-11-26 | 1 | 1 |
| [sase-1vd.5](sase-1vd.5.md) | Conservative found-in-text detection | ◐ in_progress | medium | 2026-11-26 | 1 | 1 |
| [sase-1vd.6](sase-1vd.6.md) | Telegram copy buttons | ✓ closed | small | 2026-11-26 | 1 | 0 |
| [sase-1vd.7](sase-1vd.7.md) | Agent guidance, contract docs, and skill rollout | ✓ closed | small | 2026-11-26 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1vd: Question copy panel [in_progress]"]
    n1["sase-1vd.1: Core copy contract and creation-time validation [closed]"]
    n2["sase-1vd.2: Generalize the Copy as palette [closed]"]
    n3["sase-1vd.3: Question copy panel behind y [closed]"]
    n4["sase-1vd.4: Discoverability cues on the question pane [closed]"]
    n5["sase-1vd.5: Conservative found-in-text detection [in_progress]"]
    n6["sase-1vd.6: Telegram copy buttons [closed]"]
    n7["sase-1vd.7: Agent guidance, contract docs, and skill rollout [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n3
    n1 -.-> n6
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n4 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.1/README.md) | [sase-1vd.1](sase-1vd.1.md) | 2 |
| [bbugyi200.athena.sase-1vd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.2/README.md) | [sase-1vd.2](sase-1vd.2.md) | 1 |
| [bbugyi200.athena.sase-1vd.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.3.md) | [sase-1vd.3](sase-1vd.3.md) | 1 |
| [bbugyi200.athena.sase-1vd.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.4.md) | [sase-1vd.4](sase-1vd.4.md) | 1 |
| [bbugyi200.athena.sase-1vd.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.5.md) | [sase-1vd.5](sase-1vd.5.md) | 1 |
| [bbugyi200.athena.sase-1vd.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.6/README.md) | [sase-1vd.6](sase-1vd.6.md) | 0 |
| [bbugyi200.athena.sase-1vd.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.7.md) | [sase-1vd.7](sase-1vd.7.md) | 0 |
| [bbugyi200.athena.sase-1vd.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.land/README.md) | [sase-1vd](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f1eaded`](https://github.com/sase-org/sase/commit/f1eaded87c8ef202309d8c6afea727122b69540f) | feat(ace): copy-as palette foundation with sections and preview pane | [sase-1vd.2](sase-1vd.2.md) | 2026-11-26 11:45:30 EST |
| sase-core | [`sase-core@76638b5`](https://github.com/sase-org/sase-core/commit/76638b579e7e937ae1d18ef677fc61ccbe5da8c0) | feat(questions): add question copy contracts | [sase-1vd.1](sase-1vd.1.md) | 2026-11-26 12:42:49 EST |
| sase | [`b9964f3`](https://github.com/sase-org/sase/commit/b9964f31a8ec7c5f68217fb1dbd4904089c3337f) | feat(questions): validate and display copy metadata | [sase-1vd.1](sase-1vd.1.md) | 2026-11-26 12:43:57 EST |
| sase | [`d88af8a`](https://github.com/sase-org/sase/commit/d88af8a00ac19ebd2d82272ffacb49abce7259df) | feat(ace): add question copy panel behind y | [sase-1vd.3](sase-1vd.3.md) | 2026-11-26 14:27:21 EST |
| sase | [`758745c`](https://github.com/sase-org/sase/commit/758745cb400d7846cd630ee0285e4a58a1036ec3) | feat(ace): show copy progress cues on the question pane | [sase-1vd.4](sase-1vd.4.md) | 2026-11-26 15:59:37 EST |
| sase-core | [`sase-core@8cb07c3`](https://github.com/sase-org/sase-core/commit/8cb07c3f4685c852c29c22869c56ede33299d00c) | feat(question-copy): add conservative text candidate detector | [sase-1vd.5](sase-1vd.5.md) | 2026-11-26 17:35:57 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vd.2][1] | Need parent epic scope for phase context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.2/README.md

<!-- sase:referenced-by:end -->
