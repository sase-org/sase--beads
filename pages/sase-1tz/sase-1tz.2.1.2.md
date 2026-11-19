# Bead: sase-1tz.2.1.2 — Render one digest line per cause with true totals, coverage, and pruning

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.2` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST · **Closed:** 2026-11-19 14:58:58 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

digest_render: the hourly digest snapshots and resets the interval counter atomically. It renders one line per cause with count, first/last time, and a sample under a true-total and coverage header, with no loss after downtime or a crash. Digest files are pruned on a 30-day horizon.

## Notes

[2026-11-19T18:28:48Z · sase-1tz.2.1.2] MEASUREMENT (read-only, before install): athena 729 digest files, 14535990 bytes, newest digest_20261119_124557.txt; apollo 440 files, 23576961 bytes, newest digest_20261119_124627.txt. After-install: ls ~/.sase/axe/error_digests | wc -l; tail -n 30 "$(ls -t ~/.sase/axe/error_digests/* | head -1)"

[2026-11-19T18:28:50Z · sase-1tz.2.1.2] PROPOSED FOLLOW-UP: tests/test_axe_state.py::test_concurrent_error_appends_are_atomic_and_lossless fails with ModuleNotFoundError: No module named tests in multiprocessing spawn workers — reproduces independently of digest_render (spawn pickle of a tests helper); error_groups sase-1tz.2.1.1 added the test.

[2026-11-19T19:14:06Z · sase-1tz.2.1.2] PROPOSED FOLLOW-UP: sibling pub_cleanup left three just-check NEW failures that reproduce identically on clean HEAD — test_macro_string_literals_avoid_xprompt_terms findings in tests/turns/test_workspace_retention_agents_scratch.py (%xprompts_enabled strings; same class as closed sase-1hr); test_cleanup_after_success_does_not_resurrect TypeError remaining_timeout vs clean() mock; extra live site src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch in test_artifact_directory_operation_sites_are_reviewed

[2026-11-19T19:55:32Z · sase-1tz.2.1.2] sase bead close refused while origin/master still lists the three consumed --epic-symbol rows; local Justfile already dropped them. Host close after this commit publishes the drop.

[2026-11-19T19:58:58Z · sase-1tz.2.1.2] Closed by explicit `sase stitch create -B close` after create_commit landed 96b3716cb3 ("feat(axe): render grouped scheduler error digests with true totals"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1tz.2.1.2` if more work remains.

## Dependencies

- **Depends on:** [sase-1tz.2.1.1](sase-1tz.2.1.1.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md) | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96b3716`](https://github.com/sase-org/sase/commit/96b3716cb32b0888fcdba7ab8861cd781087d973) | feat(axe): render grouped scheduler error digests with true totals | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 2026-11-19 14:57:27 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.2][1] | Need remaining notes, description details, and work already done | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md

<!-- sase:referenced-by:end -->
