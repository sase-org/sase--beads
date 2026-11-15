# Bead: sase-1sy.1 — K on a bead opens a bead card

[Bead Pages](../README.md) / [sase-1sy](README.md) / sase-1sy.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.dy` · **Assignee:** `sase-1sy.1` · **Size:** medium
**Created:** 2026-11-14 09:04:05 EST · **Closed:** 2026-11-15 08:25:53 EST
**Plan:** [202611/bead\_k\_preview.md](https://github.com/sase-org/sase--plans/blob/main/202611/bead_k_preview.md)

## Description

peek: recognize bare and @bead: IDs at the cursor, route them through a warm app-level bead store directory, splice the bead step into the K chain with a byte-for-byte resume of the word lookup for non-beads, and ship the BeadPreviewModal core (title, chips, description, property grid, copy/plan actions, loading state).

## Notes

[2026-11-15T13:25:53Z · sase-1sy.1] Peek phase: K on bare IDs and @bead:/bead: refs opens BeadPreviewModal via a warm app-level store directory. Unowned prefixes stay on the sync word-lookup path; owned misses thread bead_miss; ref misses toast without lookup. Card shows identity, chips, description, property grid, copy/plan actions, and loading. Verified with sase tool run check (5b2483019fce14879240045d60a8d63f).

## Dependencies

- **Blocks:** [sase-1sy.2](sase-1sy.2.md) ✓ · ⧖ 2026-11-14
- **Blocks:** [sase-1sy.3](sase-1sy.3.md) ◐ · ⧖ 2026-11-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sy.1/README.md) | [sase-1sy.1](sase-1sy.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4006ec3`](https://github.com/sase-org/sase/commit/4006ec36adf88bfc2a1691432e48b62b00018eb5) | feat(tui): preview beads with K in the prompt input | [sase-1sy.1](sase-1sy.1.md) | 2026-11-15 08:29:32 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sy.1][1] | Need full notes and remaining work for this phase | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sy.1/README.md

<!-- sase:referenced-by:end -->
