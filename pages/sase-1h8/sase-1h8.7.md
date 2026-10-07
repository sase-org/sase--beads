# Bead: sase-1h8.7 — One store read per CLI command

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.7` · **Size:** medium
**Created:** 2026-10-06 18:59:37 EDT · **Closed:** 2026-10-06 23:53:27 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

one-replay: route targets without a full read, resolve inside the locked mutation load, and collapse the Python lanes' redundant resolve/show calls so each command reads the store once.

## Notes

[2026-10-07T03:22:57Z · sase-1h8.7--1] After one-replay read counts (tests/test_bead/test_cli_store_read_counts.py, 11 passed): update 1, update --note 3, close 2, close --note 2, note 2, note --remove 2, create --parent 1, open 1, dep add 1, dep rm 1, rm 1. Routing (bead_route_targets) and target probing (bead_probe_target_owner) never load the store and are excluded from the counts.

[2026-10-07T03:53:06Z · sase-1h8.7--2] This turn fixed forward 9 check failures: (1) operation_context lazy registry read restores local-first (routing acceptance + operation_context tests), (2) removed premature Rust-verb gate in bead_fast_path (fast-path guard + attach +1 tests), (3) update --note dedup by resolved ID with per-input echo expansion (bulk timestamp test), (4) updated 4 stale delegation assertions to in-mutation resolution per phase design (show x2, remove_many, update_many). read_counts 11 passed; focused bead suites 92 passed; fmt/ruff/mypy clean. grok Enterprise probe + ace overlapping-checkouts flakes pass in isolation.

[2026-10-07T03:53:27Z · sase-1h8.7--2] One-replay verified: read_counts 11 passed (update 1, update -n 3, close 2, close --note 2, note 2, note --remove 2, create --parent 1, open 1, dep add 1, dep rm 1, rm 1); focused suites 92 passed (routing, operation_context, fast_path, attach, bulk, delegation); fmt/ruff/mypy clean; epic-symbols empty. Prior full check had 9 bead failures now fixed forward plus 2 load flakes (grok probe, ace checkout overlap) that pass in isolation.

## Dependencies

- **Blocks:** [sase-1h8.11](sase-1h8.11.md) ◐ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.12](sase-1h8.12.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.4](sase-1h8.4.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.7.md) | [sase-1h8.7](sase-1h8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bff4860`](https://github.com/sase-org/sase-core/commit/bff4860c273afc0270248c6eeb203dddda466435) | feat(bead): one-replay core support for in-mutation resolution and target probing | [sase-1h8.7](sase-1h8.7.md) | 2026-10-07 00:01:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.7--2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.7.md

<!-- sase:referenced-by:end -->
