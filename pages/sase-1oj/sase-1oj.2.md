# Bead: sase-1oj.2 — Self-heal the corrupt bead read-model cache

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.2` · **Size:** medium
**Created:** 2026-10-26 16:07:27 EDT · **Closed:** 2026-10-26 17:24:44 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Description

core-read-model-heal: in sase-core's bead read model, classify SQLITE_CORRUPT write faults and repair them by REINDEX or an in-place table recreate. Stop swallowing invalidation failures, back off after failed rebuilds, never downgrade a newer cache, and add a regression test that reproduces athena's corrupt meta index.

## Notes

[2026-10-26T21:24:44Z · sase-1oj.2] Implemented in-place read-model corruption repair, surfaced invalidation diagnostics, protected newer-version caches, and added process-local rebuild backoff. Verified with `sase tool run check` (exit 0); all four new corruption/version/backoff unit tests passed. `sase bead epic-symbols sase-1oj.2` reported no leftovers.

## Dependencies

- **Blocks:** [sase-1oj.3](sase-1oj.3.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oj.4](sase-1oj.4.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.2/README.md) | [sase-1oj.2](sase-1oj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@651d193`](https://github.com/sase-org/sase-core/commit/651d19330651f911ffdf20c8768d7b3a3d5e2634) | fix(bead-read-model): repair corrupt caches in place | [sase-1oj.2](sase-1oj.2.md) | 2026-10-26 18:05:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oj.2][1] | Check whether earlier work left a recorded remainder before planning | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.2/README.md

<!-- sase:referenced-by:end -->
