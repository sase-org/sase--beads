# Bead: sase-1lc.8.1 — Realign the sase-core clan wave wire and switch the adapter to it

[Bead Pages](../README.md) / [sase-1lc.8](sase-1lc.8.md) / sase-1lc.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lc.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.land.md) · **Assignee:** `sase-1lc.8.1` · **Size:** medium
**Created:** 2026-10-15 23:30:16 EDT · **Closed:** 2026-10-16 00:43:29 EDT
**Plan:** [202610/clan\_waves\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/clan_waves_landing_repairs.md)

## Description

wire: replace project_clan_waves' partial wire with the planned key-based layout wire in sase-core (allow_threads, serde defaults, the missing tests). Make the Python facade and adapter consume it and delete the Python-side rank, layered, ghost-split, and ordering derivations, with no visible change.

## Notes

[2026-10-16T04:43:15Z · sase-1lc.8.1--1] PROPOSED FOLLOW-UP: Fix generated-doc formatting drift — `sase tool run check` stops at fmt-docs-check because render_glossary and render_design_decisions differ from Prettier output; the epic plan identifies this as known and tracked by docs epic sase-1le.

[2026-10-16T04:43:29Z · sase-1lc.8.1--1] Verified the sase-core check passed after correcting two clippy findings and the ghost-wave test expectation; just fix passed; the changed clan-wave adapter test passed; tui_import_closure --diff HEAD reports +0 modules. The primary sase tool run check stops at the known fmt-docs-check drift in render_glossary/render_design_decisions tracked by sase-1le; recorded as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Blocks:** [sase-1lc.8.2](sase-1lc.8.2.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lc.8.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.1.md) | [sase-1lc.8.1](sase-1lc.8.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4c83f2d`](https://github.com/sase-org/sase-core/commit/4c83f2de965791ae78a2d0a6a12c823ebc76d2eb) | feat(clan-waves): return key-based layout wire | [sase-1lc.8.1](sase-1lc.8.1.md) | 2026-10-16 00:44:27 EDT |
| sase | [`04fee05`](https://github.com/sase-org/sase/commit/04fee055590e2fe67b072b5cd88b1ebd2c6e779f) | feat(ace): consume key-based clan wave layout wire | [sase-1lc.8.1](sase-1lc.8.1.md) | 2026-10-16 00:49:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lc.8.1--1][1] | Verify the assigned phase closed with its check evidence | 2 |
| read-by | [agent:sase-1lc.8.land--2][2] | closeout reread children | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.land.md

<!-- sase:referenced-by:end -->
