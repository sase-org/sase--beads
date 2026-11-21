# Bead: sase-1uu.3 — Stream per-stage progress from agent\_publication project drains

[Bead Pages](../README.md) / [sase-1uu](README.md) / sase-1uu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ew](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ew.md) · **Assignee:** `sase-1uu.3` · **Size:** small
**Created:** 2026-11-21 10:59:31 EST · **Closed:** 2026-11-21 13:06:20 EST
**Plan:** [202611/artifact\_link\_aggregate\_timeouts.md](https://github.com/sase-org/sase--plans/blob/main/202611/artifact_link_aggregate_timeouts.md)

## Description

Give drain_project a progress callback, so a slow or killed agent_publication tick leaves breadcrumbs for the stage it was in. Log the link drain's phase timings, including the new publish sub-phases, the same way artifact_link_backfill already logs its drain phases.

## Notes

[2026-11-21T18:06:11Z · sase-1uu.3] PROPOSED FOLLOW-UP: docs-lint fails on clean base - docs/reference/automation/notification-gates.md is 6158 words, over the 6000 cap (grew in da2165b80f); split or trim it.

[2026-11-21T18:06:20Z · sase-1uu.3] drain_project takes progress=; stage lines (hood batch n (k keys), link store resolve, link drain (m agents), referenced-by drain, quarantine sweep) emitted before each stage, plus a 'link drain phases:' line with publish.* and skipped; _run_publication_job passes a _maybe_progress-gated callback with project= suffix. ChopLogger.info already flushes per line. New tests in test_publication_slow_pass_progress.py pass; mypy/ruff/fmt clean. just check: only unrelated failures (docs word-budget on clean base, load-flaky test_sdd_commit/gate_capacity that pass in isolation).

## Dependencies

- **Depends on:** [sase-1uu.2](sase-1uu.2.md) ✓ · ⧖ 2026-11-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1uu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.3/README.md) | [sase-1uu.3](sase-1uu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`333f244`](https://github.com/sase-org/sase/commit/333f244b50e593996f65e34e9f5aa25cb006316f) | feat(agent-publication): stream per-stage progress from project drains | [sase-1uu.3](sase-1uu.3.md) | 2026-11-21 13:07:52 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1uu.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.3/README.md

<!-- sase:referenced-by:end -->
