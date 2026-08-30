# Bead: sase-vw.4 — Linked References output

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.4` · **Size:** medium
**Created:** 2026-08-30 10:02:17 EDT · **Closed:** 2026-08-30 11:59:31 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

render: emit a numbered `## Linked References` section for every note and web unit across the markdown, rich, and json formats, and carry link data in the JSON payloads.

## Notes

[2026-08-30T15:59:31Z · sase-vw.4] just check passed. Markdown, rich, and JSON emit a numbered Linked References section for notes and web units (after Children when present), omit it when a unit has no reference links, list unresolved last, mark core notes and web descriptors as always-loaded, skip targets already inline-expanded in the same section, and list depth-truncated inline links as references. JSON carries linked_references on note and web-section payloads and a links list on note/node objects. Single-note show/read stay byte-identical; audited byte_count still counts only printed content, not the listing. A gates-never-block fixture inlines single-turn-agents at the bottom with no Linked References listing.

## Dependencies

- **Depends on:** [sase-vw.3](sase-vw.3.md) ✓ · ⧖ 2026-08-30
- **Blocks:** [sase-vw.5](sase-vw.5.md) ◐ · ⧖ 2026-08-30
- **Blocks:** [sase-vw.6](sase-vw.6.md) ◐ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.4/README.md) | [sase-vw.4](sase-vw.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`40cd8ce`](https://github.com/sase-org/sase/commit/40cd8ce6eaf4204f7cf55eab58193841f98a911e) | feat(memory): render Linked References for show and read | [sase-vw.4](sase-vw.4.md) | 2026-08-30 12:00:46 EDT |
