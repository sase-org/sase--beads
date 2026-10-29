# Bead: sase-1pm.1 — Count stitch SHA receipts as successful commits (sase-1nh)

[Bead Pages](../README.md) / [sase-1pm](README.md) / sase-1pm.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15r.md) · **Assignee:** `sase-1pm.1` · **Size:** small
**Created:** 2026-10-29 01:44:35 EDT · **Closed:** 2026-10-29 03:22:03 EDT
**Plan:** [202610/task\_backlog\_epic\_1.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_1.md)

## Description

receipt: accept the SHA results write_result_marker actually writes, so passing prepared-completion monitors stop launching recovery successors; make the tests use production-shaped markers.

## Notes

[2026-10-29T07:21:36Z · sase-1pm.1] PROPOSED FOLLOW-UP: just-check leftovers fail identically on clean base dd59c28f44 — test_artifact_directory_operation_sites_are_reviewed (owned by sibling phase audit/sase-1p5), test_contract_manifest_matches_marker_selection (stale contract_manifest.txt), monitor supervisor kill + identity-scrub tests (timing-sensitive under load)

[2026-10-29T07:21:54Z · sase-1pm.1] TASK RESOLVED: sase-1nh — _marker_is_successful now accepts production SHA markers (result=short SHA consistent with commit_sha) as well as legacy ok; unpushed/dispatch-error/PR-URL/diff-path markers still fail. Regression test_production_sha_receipt_completes_without_recovery fails pre-fix, passes post-fix; all 9 tests in tests/monitor/test_monitor_host_completion.py pass; ruff + mypy clean; just check (run 08a3ec703c011e1cfebd914eddaa5095) green except 4 failures that reproduce identically on clean base.

[2026-10-29T07:22:03Z · sase-1pm.1] SHA receipts count as success: new regression fails pre-fix/passes post-fix; 9/9 host-completion tests pass; ruff+mypy clean; just check green except 4 base-identical pre-existing failures (see PROPOSED FOLLOW-UP note)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pm.1/README.md) | [sase-1pm.1](sase-1pm.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pm.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pm.1/README.md

<!-- sase:referenced-by:end -->
