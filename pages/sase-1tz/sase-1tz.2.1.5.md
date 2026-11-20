# Bead: sase-1tz.2.1.5 — Bound inventory\_build with reuse, an incremental history cache, and scoped queries

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.5` · **Size:** medium
**Created:** 2026-11-19 11:13:27 EST · **Closed:** 2026-11-19 19:58:51 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_inventory: build the hood inventory once per project per tick instead of once per batch. Cache parsed primary-history trailers by HEAD and parse only new commits. Scope index and dismissed-record queries to the requested hoods, and give inventory_build its own deadline slice.

## Notes

[2026-11-20T00:58:51Z · sase-1tz.2.1.5--2] Implemented per-project inventory reuse, incremental history caching, scoped index and dismissed-record queries, and the inventory_build deadline. Fixed the reported optional-identity typing, test wait pragma, and verification test setup. Verified with green sase tool run check 0cbbcaa04251b606dc6f364ace0bb0a8 and seven focused regression tests.

## Dependencies

- **Depends on:** [sase-1tz.2.1.3](sase-1tz.2.1.3.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.4](sase-1tz.2.1.4.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md) | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@80fcc86`](https://github.com/sase-org/sase-core/commit/80fcc862ba4b10c936eb6b484470632729eefbc3) | feat(agent-archive): filter dismissed bundles by identity prefix | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2026-11-19 20:12:40 EST |
| sase | [`fb85972`](https://github.com/sase-org/sase/commit/fb85972f27438a2ceee0304862aaa3446106fb80) | perf(agents-sync): reuse scoped hood inventory | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2026-11-19 21:01:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.5--2][1] | Need assigned phase scope while attributing the verification failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md

<!-- sase:referenced-by:end -->
