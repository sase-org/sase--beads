# Bead: sase-w3.2 — Panes resolve refs; the follow path addresses by canonical ref

[Bead Pages](../README.md) / [sase-w3](README.md) / sase-w3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.b](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.b.md) · **Assignee:** `sase-w3.2` · **Size:** medium
**Created:** 2026-09-03 12:48:28 EDT · **Closed:** 2026-09-04 06:48:58 EDT
**Plan:** [202609/link\_follow\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/link_follow_reliability.md)

## Description

pane-ref-resolvers: add entry_target_for_ref to the ArtifactEntryNavigator contract, implement it per pane from unfiltered snapshots, address link follows by canonical ref with the chip target demoted to a routing hint, stop passing RelationRole.FAMILY, and fix _change_query_for_navigation reporting success on a selection miss.

## Dependencies

- **Depends on:** [sase-w3.1](sase-w3.1.md) ✓ · ⧖ 2026-09-03
- **Blocks:** [sase-w3.3](sase-w3.3.md) ◐ · ⧖ 2026-09-03

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b93a189`](https://github.com/sase-org/sase/commit/b93a1894ddc88153bc85446a029092097cc393b3) | feat: Panes resolve refs; the follow path addresses by canonical ref (sase-w3.2) | [sase-w3.2](sase-w3.2.md) | 2026-09-04 06:47:49 EDT |
