# Bead: sase-vw — Memory link reference and rendering strategies

[Bead Pages](../README.md) / sase-vw

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.land`
**Created:** 2026-08-30 10:02:14 EDT · **Closed:** 2026-08-30 14:04:34 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/memory_link_strategies.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md

<!-- sase:links:end -->

## Description

Memory notes, web descriptors, and strands declare how links to other memory files are detected and rendered, `[[target]]` / `![[target]]` links resolve and render in `sase memory show`/`read`, and the existing corpus links itself.

## Notes

[2026-08-30T18:04:34Z · sase-vw.land--1] Verified all 8 phases against source and the 8 epic commits (ae83faa2e..4509c9d67): link_reference/link_rendering frontmatter with strand>web>default precedence and the closure: legacy alias; the [[target]]/![[target]] scanner (code zones skipped, confirmed on xprompts.md) and four-form resolver; inline edges folded into the closure BFS with cross-web/cross-note extra roots; numbered Linked References across markdown, rich, and json; glossary migrated to implicit/inline and decisions off closure: none; Related Task Types on generated task-type strands; the hand-authored corpus linked plus the decisions:memory-links-are-authored record; docs/skill/README updates. Acceptance checks all pass: decisions:gates-never-block inlines single-turn-agents, lint_and_test.md lists two-speed-verification and symvision.md, task_types:bug lists ci and flake, glossary json intact, sase doctor -C config.memory_webs OK.

Landing fixed five things the phases left: (1) sase-vw.7 self-listing bug - a web section listed targets it already rendered, so a back-link from an inlined strand listed the requested strand itself; selector.py now excludes any already-rendered same-web target for reference edges too, with two regression tests. (2) sase-vw.5 proposal - sase_memory_read.md and docs/ace.md still described glossary via the retired closure: mentions key; both now describe link_reference: implicit and authored links. (3) sase/memory/README.md was never regenerated after sase-vw.8 changed memory-README.template.md; ran sase memory init (project + chezmoi home now in sync). (4) tests/completion/snapshots/cli_spec.json was never resynced after sase-vw.8 changed parser_memory.py help text - two tests failed at HEAD; ran just sync-completion-spec. (5) MemoryWeb.closure/WebClosureMode became dead once the ACE web card stopped rendering a Closure row (now Links: <reference> . <rendering>), so both were deleted per the plan preference.

Integration: reviewed every non-epic commit since ae83faa2e - cccacb98b (memory bullet reorder, core memory sase.md, no link work owed), 0fd1cc6c1 and fdb962c13 (notification modal, gate-shell buckets, unrelated). No conflicts.

Follow-up proposals, all resolved without new beads: sase-vw.1 #1, sase-vw.3 #1, and sase-vw.6 #1 reported pre-existing init-memory AGENTS.md heading failures and sase-vw.1 #2 reported an ACE/LSP wait-prose failure - all six tests pass on this tree after just install, so they were stale-workspace artifacts, not real defects; sase-vw.3 #1 also flagged init memory --check drift, which was the epic-caused README staleness fixed above; sase-vw.3 #2 was a scope note, not a task, and both of its decisions are now documented in docs/memory.md. sase-vw.5 #1 and sase-vw.7 #1 were fixed as epic work. No --epic-symbol entries. just check-full green.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-vw.1](sase-vw.1.md) | Link strategy frontmatter | ✓ closed | medium | 2026-08-30 | 1 | 1 |
| [sase-vw.2](sase-vw.2.md) | Link scanner and target resolver | ✓ closed | medium | 2026-08-30 | 1 | 1 |
| [sase-vw.3](sase-vw.3.md) | Links in the closure walk | ✓ closed | medium | 2026-08-30 | 1 | 1 |
| [sase-vw.4](sase-vw.4.md) | Linked References output | ✓ closed | medium | 2026-08-30 | 1 | 1 |
| [sase-vw.5](sase-vw.5.md) | Declare existing web strategies | ✓ closed | small | 2026-08-30 | 1 | 1 |
| [sase-vw.6](sase-vw.6.md) | Generated task-type strand links | ✓ closed | small | 2026-08-30 | 1 | 1 |
| [sase-vw.7](sase-vw.7.md) | Link the existing corpus | ✓ closed | medium | 2026-08-30 | 1 | 1 |
| [sase-vw.8](sase-vw.8.md) | Skill and documentation updates | ✓ closed | small | 2026-08-30 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-vw: Memory link reference and rendering strategies [closed]"]
    n1["sase-vw.1: Link strategy frontmatter [closed]"]
    n2["sase-vw.2: Link scanner and target resolver [closed]"]
    n3["sase-vw.3: Links in the closure walk [closed]"]
    n4["sase-vw.4: Linked References output [closed]"]
    n5["sase-vw.5: Declare existing web strategies [closed]"]
    n6["sase-vw.6: Generated task-type strand links [closed]"]
    n7["sase-vw.7: Link the existing corpus [closed]"]
    n8["sase-vw.8: Skill and documentation updates [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n7
    n5 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.1/README.md) | [sase-vw.1](sase-vw.1.md) | 1 |
| [bbugyi200.athena.sase-vw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.2/README.md) | [sase-vw.2](sase-vw.2.md) | 1 |
| [bbugyi200.athena.sase-vw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.3/README.md) | [sase-vw.3](sase-vw.3.md) | 1 |
| [bbugyi200.athena.sase-vw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.4/README.md) | [sase-vw.4](sase-vw.4.md) | 1 |
| [bbugyi200.athena.sase-vw.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.5/README.md) | [sase-vw.5](sase-vw.5.md) | 1 |
| [bbugyi200.athena.sase-vw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.6/README.md) | [sase-vw.6](sase-vw.6.md) | 1 |
| [bbugyi200.athena.sase-vw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.7/README.md) | [sase-vw.7](sase-vw.7.md) | 1 |
| [bbugyi200.athena.sase-vw.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.8/README.md) | [sase-vw.8](sase-vw.8.md) | 1 |
| [bbugyi200.athena.sase-vw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vw.land.md) | [sase-vw](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae83faa`](https://github.com/sase-org/sase/commit/ae83faa2e020c5b9966badd44a0758b4cb271331) | feat(memory): add authored link scanner and resolver | [sase-vw.2](sase-vw.2.md) | 2026-08-30 10:47:13 EDT |
| sase | [`7c8117b`](https://github.com/sase-org/sase/commit/7c8117b17e92674f99f52d98f2a44ad5481f86b8) | feat(memory): add link\_reference and link\_rendering frontmatter | [sase-vw.1](sase-vw.1.md) | 2026-08-30 10:50:34 EDT |
| sase | [`90e3a38`](https://github.com/sase-org/sase/commit/90e3a385c526e7659b93b29a5ce599d1e6deade6) | feat(memory): fold authored links into the closure walk | [sase-vw.3](sase-vw.3.md) | 2026-08-30 11:32:44 EDT |
| sase | [`40cd8ce`](https://github.com/sase-org/sase/commit/40cd8ce6eaf4204f7cf55eab58193841f98a911e) | feat(memory): render Linked References for show and read | [sase-vw.4](sase-vw.4.md) | 2026-08-30 12:00:46 EDT |
| sase | [`19a77ee`](https://github.com/sase-org/sase/commit/19a77eea96af28f13f973f191cc0415afd1fcf3d) | feat(memory): emit Related Task Types links on generated strands | [sase-vw.6](sase-vw.6.md) | 2026-08-30 12:34:28 EDT |
| sase | [`70dd1da`](https://github.com/sase-org/sase/commit/70dd1da6174fe18fa264d5cbf1247daaaf88e8df) | feat(memory): declare existing web link strategies | [sase-vw.5](sase-vw.5.md) | 2026-08-30 12:40:50 EDT |
| sase | [`8a377b0`](https://github.com/sase-org/sase/commit/8a377b0704e211eb18839fab5b5acd12a8c40956) | docs(memory): document memory link syntax and target forms | [sase-vw.8](sase-vw.8.md) | 2026-08-30 12:48:20 EDT |
| sase | [`4509c9d`](https://github.com/sase-org/sase/commit/4509c9d675eaa21485063d99a386c947ab52021a) | docs(memory): link the existing corpus and record authored memory links | [sase-vw.7](sase-vw.7.md) | 2026-08-30 13:10:44 EDT |
| sase | [`467d3de`](https://github.com/sase-org/sase/commit/467d3dee47f8a12dadfc6600fc2274ca170787c6) | fix(memory): resolve sase-vw landing gaps in authored memory links | [sase-vw](README.md) | 2026-08-30 14:06:46 EDT |
