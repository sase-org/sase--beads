# Bead: sase-k2.6 — Bounded per-pass cost for the PR mirror

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.6` · **Size:** medium
**Created:** 2026-08-12 11:31:05 EDT · **Closed:** 2026-08-12 14:09:01 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

perf: stop re-reading and re-parsing the whole active-plus-archive ProjectSpec index once per mutation in both the sync loop and the importer, replacing it with one locked batch apply over an incrementally maintained index.

## Notes

[2026-08-12T18:09:01Z · sase-k2.6] Implemented locked batched external PR import/sync with incremental in-memory Patch index updates; verified .venv/bin/pytest tests/test_external_pr_importer.py tests/test_external_pr_sync.py, just _lint-symvision, git diff --check, and just check (scoped lane escalated to full suite).

[2026-08-12T18:10:20Z · sase-k2.6] Verified .venv/bin/pytest tests/test_external_pr_importer.py tests/test_external_pr_sync.py; just _lint-symvision; git diff --check; just check passed with scoped lane escalating to the full suite.

## Dependencies

- **Depends on:** [sase-k2.1](sase-k2.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k2.5](sase-k2.5.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k2.6/README.md) | [sase-k2.6](sase-k2.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`32ccc9e`](https://github.com/sase-org/sase/commit/32ccc9eb79ef98fa9359cdf2e1105857bbe8d57d) | perf: batch external PR mirror imports | [sase-k2.6](sase-k2.6.md) | 2026-08-12 14:11:32 EDT |
