# Bead: sase-1gt.1 — Unblock Publish release-metadata sync

[Bead Pages](../README.md) / [sase-1gt](README.md) / sase-1gt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ww](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ww.md) · **Assignee:** `sase-1gt.1` · **Size:** small
**Created:** 2026-10-05 12:16:21 EDT · **Closed:** 2026-10-05 13:09:28 EDT
**Plan:** [202610/fix\_sase\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202610/fix_sase_ci_failures.md)

## Description

release-metadata: make tools/ratchet_core_window ignore the uv lockfile `revision` header that newer uv bumps on every rewrite, add guardrail tests, and commit a refreshed uv.lock so `uv lock --check` passes on master again.

## Notes

[2026-10-05T17:09:14Z · sase-1gt.1--1] PROPOSED FOLLOW-UP: tests/tool/test_demand_runs.py::test_foreground_run_records_context_usage_and_grant is flaky under parallel load — failed in full just check run with peak_tree_rss_kib==0 (loadavg ~13, 6 workers) but passes in isolation; unrelated to release-metadata change (zero file overlap)

[2026-10-05T17:09:28Z · sase-1gt.1--1] Verified: tools/ratchet_core_window ignores uv lock revision header; 7/7 guardrail tests pass; uv lock --check exits 0; full just check has no related failures (1 unrelated RSS-sampling flake passes in isolation, 2 KNOWN)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gt.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.1.md) | [sase-1gt.1](sase-1gt.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b3e571a`](https://github.com/sase-org/sase/commit/b3e571a8ab0cce87432397a5cd6d01ca1cf4cbc4) | fix(release): ignore uv lock revision header in ratchet\_core\_window | [sase-1gt.1](sase-1gt.1.md) | 2026-10-05 13:10:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gt.1--1][1] | Need phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.1.md

<!-- sase:referenced-by:end -->
