# Bead: sase-sq.1 — Core and reference memory vocabulary

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.1` · **Size:** large
**Created:** 2026-08-24 09:32:13 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

tiers: rename short-term/long-term memory to core/reference across the Rust tier wire, note frontmatter, AGENTS.md anchors, templates, skills, docs, and prose, accepting the old spelling forever and migrating existing notes in place.

## Notes

[2026-08-24T15:23:52Z · sase-sq.1] PROPOSED FOLLOW-UP: After the sase-core release carrying core/reference memory tiers is published, bump the sase-core-rs floor in sase so CI and fresh installs no longer rely on the linked checkout build.

[2026-08-24T15:24:19Z · sase-sq.1] PROPOSED FOLLOW-UP: Regenerate bob-cli memory after this change has landed and the released sase on PATH understands canonical type: core and type: reference frontmatter.

[2026-08-24T15:24:44Z · sase-sq.1] PROPOSED FOLLOW-UP: Run sase skill init after landing so the generated /sase_memory_read skill deployed to managed locations uses reference-memory vocabulary.

[2026-08-24T15:25:06Z · sase-sq.1] PROPOSED FOLLOW-UP: Regenerate src/sase/memory/assets/memory-directory-map.png and update memory-directory-map.prompt.md together so the diagram labels move from short/long to core/reference without prompt/image drift.

[2026-08-24T15:25:27Z · sase-sq.1] PROPOSED FOLLOW-UP: Do a separate internal identifier rename for legacy short/long symbol names such as GeneratedLongMemoryNote, _short_memory_bodies, and inlined_short_memory_files once the user-facing vocabulary change is landed.

## Dependencies

- **Blocks:** [sase-sq.2](sase-sq.2.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.1.md) | [sase-sq.1](sase-sq.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9ca0db`](https://github.com/sase-org/sase/commit/c9ca0db5f8d0d7b5d007010e661abb1d2b5638dc) | feat(memory): rename memory tiers to core and reference | [sase-sq.1](sase-sq.1.md) | 2026-08-24 12:41:31 EDT |
