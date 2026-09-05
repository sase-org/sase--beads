# Bead: sase-wn.6 — Cache immutable axe status reads in ace

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.6` · **Size:** medium
**Created:** 2026-09-04 12:11:09 EDT · **Closed:** 2026-09-04 22:14:57 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-axe-status-cache: stop collect_axe_status_data re-parsing ~600 files per tick - cache immutable chop run records by (path, mtime), tail logs only when they grew, and collect full chop snapshots only when the Axe tab needs them.

## Notes

[2026-09-05T02:14:12Z · sase-wn.6] PROPOSED FOLLOW-UP: rust sha: query matches mid-string — tests/test_query_profile_corpus_facade.py::test_sha_field_matches_prefix_not_mid_string_through_rust fails because sha:cdef matches abcdef1234567890; prefix-only is required, independent of axe status caching

[2026-09-05T02:14:57Z · sase-wn.6] Cached axe status reads: run JSON keyed by (path, mtime_ns, size), indexes reread only on mtime change, lumberjack/chop logs tailed only when size grew, per-run tails limited to the rendered chop, and full chop snapshots collected only on the Axe tab / first load / sanity reconcile. Off-tab apply keeps the last full chop cache. Verified: collector/cache/refresh tests (70) plus axe nav/startup (43) pass; ruff/mypy/symvision green. A quiet second collect of unchanged run files does zero JSON parses and zero content file opens. just check lint passed; its scoped lane escalated to the full suite after just install changed the sase_core_rs extension, then hit an unrelated rust sha: prefix-match failure (noted as PROPOSED FOLLOW-UP) plus two flakes that passed on retry.

## Dependencies

- **Depends on:** [sase-wn.5](sase-wn.5.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.6/README.md) | [sase-wn.6](sase-wn.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0927b10`](https://github.com/sase-org/sase/commit/0927b10928b344372127ac956226855f6ccb8b44) | perf(ace): cache immutable axe status reads across ticks | [sase-wn.6](sase-wn.6.md) | 2026-09-04 22:30:20 EDT |
