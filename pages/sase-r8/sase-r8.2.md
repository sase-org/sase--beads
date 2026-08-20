# Bead: sase-r8.2 — Link graph types and managed tables in sase-core

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.2` · **Size:** medium
**Created:** 2026-08-19 19:16:35 EDT · **Closed:** 2026-08-19 19:50:44 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

core: add the link-row wire types, relation registry, ManagedTableBlock primitive, Links table, companion paths, and bead link events.

## Notes

[2026-08-19T23:50:44Z · sase-r8.2] Implemented the sase-core artifact_link module: v2 link-row wire types with canonicalize/validate/upsert and undirected related dedup; closed v1 relation registry (inverses + reserved blocks/depends-on pointing at sase bead dep); ManagedTableBlock extracted from referenced_by with byte-stable referenced_by_block_* facades; top-anchored Links tables after frontmatter/plan header that do not trip header-invalid; companion naming with stem.md collision fallback to stem.ext.md; stitch has no md file; unpublished file pages under ~/.sase/artifacts/pages; tolerant links: frontmatter inlet that leaves mkdocs shapes unrecognized; BeadEventOperationWire::{LinkAdded,LinkRemoved} plus IssueWire.links with serde default. Verified ./scripts/check.sh fmt, clippy, and test (full workspace) in sase-core. No --epic-symbol leftovers. No sase user-reaching behavior and no sase-core-rs floor bump (store phase).

[2026-08-19T23:52:49Z · sase-r8.2] Implemented sase-core artifact_link: v2 link-row types, relation registry, ManagedTableBlock, Links tables, companion paths, frontmatter inlet, LinkAdded/LinkRemoved events, and IssueWire.links. Verified ./scripts/check.sh fmt, clippy, and test in sase-core. No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-r8.3](sase-r8.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.2/README.md) | [sase-r8.2](sase-r8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3eb2a6e`](https://github.com/sase-org/sase-core/commit/3eb2a6e200f23bed460a5ec509e1207e6917ff6a) | feat(artifact\_link): add link-row types, managed tables, and bead events | [sase-r8.2](sase-r8.2.md) | 2026-08-19 19:53:29 EDT |
