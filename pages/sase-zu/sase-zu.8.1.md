# Bead: sase-zu.8.1 — Make the parity oracle exercise production history and refresh paths

[Bead Pages](../README.md) / [sase-zu.8](sase-zu.8.md) / sase-zu.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.1` · **Size:** medium
**Created:** 2026-09-13 10:21:14 EDT · **Closed:** 2026-09-13 11:06:57 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

production-oracle: extend the harness to reproduce unseen artifacts, conflicting machine provenance, settled bounded queries and query-keyed refresh invalidation through production entry points.

## Notes

[2026-09-13T15:02:33Z · sase-zu.8.1] PROPOSED FOLLOW-UP: just lint symvision gate fails on unrelated pre-existing code — apply_resume_adoption in src/sase/monitor/resume.py is flagged unused-public (introduced by 897147eac2, unrelated to sase-zu load-tiering); reproduce with `just lint` and either privatize/use/delete it.

[2026-09-13T15:04:57Z · sase-zu.8.1] PROPOSED FOLLOW-UP: tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name fails pre-existing (unrelated to sase-zu) — installed sase_core_rs dev extension is missing continuation_decide_resume_adoption, which src/sase/monitor/resume.py (897147eac2) already calls; likely the linked sase-core sidecar checkout used by `just install` needs updating to a commit that exports it. Same root cause as the symvision apply_resume_adoption note above.

[2026-09-13T15:06:57Z · sase-zu.8.1] Extended tests/perf/agent_load_tiering_harness.py with production_bounded/production_full_history load paths that call load_tiered_agents (the real TUI entry point) instead of only the harness's raw index-facade probes, so the oracle exercises production's forced-revalidate full-history freshness and real query-pushdown compilation, distinguished from the pre-existing cached-freshness index_bounded/index_full_history probes. Added write_completed_artifact/set_artifact_hidden/delete_artifact/rebuild_index fixture helpers to tests/perf/agent_load_tiering_fixture.py for post-index-build mutation. Added tests/test_agent_load_tiering_production_oracle.py (8 tests, both query dialects where fair): diagnostics reproducing the two audit failures (false full-history completeness after a post-index-build artifact; conflicting-provenance machine:apollo under-selection) plus a third discovered defect (a deleted artifact keeps serving as a stale full-history row) as green diagnostics documenting current buggy behavior per the plan's no-red-suite instruction, alongside regressions proving revalidate DOES repair already-indexed hidden/mutated rows and that full history correctly settles rows beyond the Tier 1 cap. Verified: ruff/mypy/fmt/feature-flags/pyscripts/test-waits/changelog/terminology lint gates pass; just test-scoped (671 files) shows zero new failures across two independent runs, and all touched/added test files pass directly. Two pre-existing, unrelated failures (symvision unused-public on src/sase/monitor/resume.py; a missing sase_core_rs binding for continuation_decide_resume_adoption) were found, confirmed unrelated via git status/stash, and recorded as PROPOSED FOLLOW-UP notes. sase bead epic-symbols sase-zu.8.1 reports no entries.

## Dependencies

- **Blocks:** [sase-zu.8.2](sase-zu.8.2.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.1/README.md) | [sase-zu.8.1](sase-zu.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`db6fd25`](https://github.com/sase-org/sase/commit/db6fd25182dbf8278b926a0b37c7acf6f685d1ed) | test(agent-load-tiering): route the parity oracle through the production TUI loader | [sase-zu.8.1](sase-zu.8.1.md) | 2026-09-13 11:08:40 EDT |
