# Bead: sase-1oe.2 — A failed core cut stops counting as red once a newer cut succeeds

[Bead Pages](../README.md) / [sase-1oe](README.md) / sase-1oe.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14h.md) · **Assignee:** `sase-1oe.2` · **Size:** small
**Created:** 2026-10-26 08:35:12 EDT · **Closed:** 2026-10-26 09:52:49 EDT
**Plan:** [202610/unblock\_e2\_release\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_release_cutover.md)

## Description

cut-red: in sase-core, handle_no_train reports CoreCutRed only when the newest decisive completed cut is a typed failure. A later successful cut supersedes a stale red cut. Rust state tests and the steward state docs row are updated.

## Notes

[2026-10-26T13:52:35Z · sase-1oe.2] cut-red implemented in sase-core working tree on parent 67b77d0561fbb07d2f5cf9c04ff695a2788b27ab (feat project-stats languages). Policy walks core.cuts newest first; first success clears CoreCutRed; first typed failure is counted red; in-flight/cancelled/skipped never clear. Host finalizer commit of this tree is the landed SHA for core-pin. sase-core sase tool run check d530318e593762d82da474f9a44c14de green. sase sase tool run check a7d649a5886a00113b1975b45442b6ca green. Did not move sase-core-revision.txt / pyproject.toml / uv.lock.

[2026-10-26T13:52:49Z · sase-1oe.2] handle_no_train reports CoreCutRed only for the newest decisive completed cut. Newer success supersedes a stale typed red; in-flight/cancelled/skipped do not clear. Tests in states.rs cover the 2026-10-24 shape, newest typed failure, cancelled/in-flight still red, counted red without diagnostics broken, superseded red without diagnostics not broken. Wire comment documents newest-first cuts. Docs row updated. sase-core check d530318e593762d82da474f9a44c14de and sase check a7d649a5886a00113b1975b45442b6ca green. Parent SHA 67b77d0561fbb07d2f5cf9c04ff695a2788b27ab; host commit of this tree is the landed SHA. epic-symbols: none for sase-1oe.2.

## Dependencies

- **Blocks:** [sase-1oe.3](sase-1oe.3.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oe.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oe.2/README.md) | [sase-1oe.2](sase-1oe.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f956906`](https://github.com/sase-org/sase-core/commit/f95690648dadfbe9a1f02e3282f1840f81ed6589) | fix(release-steward): treat only the newest decisive core cut as red | [sase-1oe.2](sase-1oe.2.md) | 2026-10-26 09:53:57 EDT |
| sase | [`6083264`](https://github.com/sase-org/sase/commit/60832648be4292fc5f49565a34b44402c40cba1b) | docs(release-train): core\_cut\_red is the newest completed core cut | [sase-1oe.2](sase-1oe.2.md) | 2026-10-26 09:56:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oe.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oe.2/README.md

<!-- sase:referenced-by:end -->
