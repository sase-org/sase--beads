# Bead: sase-1n6.5.1.1 — Define the qualification inventory and fail-closed evaluator

[Bead Pages](../README.md) / [sase-1n6.5.1](sase-1n6.5.1.md) / sase-1n6.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) · **Assignee:** `sase-1n6.5.1.1` · **Size:** medium
**Created:** 2026-10-19 20:21:18 EDT · **Closed:** 2026-10-19 21:08:47 EDT
**Plan:** [202610/published\_core\_qualification.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md)

## Description

evidence: add the versioned N1 inventory, typed evidence schema, qualification evaluation and bounded-rerun decision, with adversarial fixtures.

## Notes

[2026-10-20T00:44:44Z · sase-1n6.5.1.1] QUALIFY CONTRACT for ci-evidence/release-wiring: `.github/release-qualification.json` schema_version=1 separates the Master Gate admission policy from release checks. Blocking qualification jobs are lint (command evidence) and test (3.12/3.13/3.14) (pytest evidence); the exercise entry names the existing four Linux/macOS wheel/sdist legs for `exercise_release`; visual-test, perf-floors, tutorial-tests, and ace-page-group-isolation are advisory. Each blocking CI entry requires completed `Write qualification evidence` and `Upload qualification evidence` job steps. `release_candidate qualify --manifest M --inventory I --jobs J --evidence-dir D --run-id R --attempt A --out O` reads normalized job-history schema_version=1: candidate identity, inventory_digest, workflow_run_id/current_attempt, and contiguous attempt snapshots with workflow_file, workflow_job_id, matrix, numeric job_id, exact job_name, workflow_run_id, execution_attempt, status, conclusion, URL, timestamps, step outcomes, and relative evidence_file. Each evidence binding carries repository, candidate_id, generation, checked_out_sha, expected_core_version, installed_core_version, inventory_digest, workflow_run_id, job_id, job_name, and attempt. Pytest evidence carries collected/passed/failed/errors/skipped, collection_failed, exit_status, first_failing_node_ids, and verbatim flaky_lines; command evidence carries completed step outcomes and missing_bindings/diagnostics, never pytest counts. `qualify` appends exact inventory bytes and loaded payloads before returning exit 2 on red; `evaluate` revalidates them and rejects bare pass, stale identity, and ambiguous history. Rerun eligibility is first-attempt test failures only; attempt 2 requires an all-test red first attempt, new evidence for rerun jobs, and unchanged proof for carried successes.

[2026-10-20T01:08:47Z · sase-1n6.5.1.1] Added versioned N1 qualification inventory and candidate-bound evaluator/CLI; focused release-candidate tests passed (62 tests); sase tool run check passed including scoped tests (13m 51s); epic-symbols clear.

## Dependencies

- **Blocks:** [sase-1n6.5.1.2](sase-1n6.5.1.2.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md) | [sase-1n6.5.1.1](sase-1n6.5.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`443fba3`](https://github.com/sase-org/sase/commit/443fba33d997ba89f189eb10ee1ff273a52eefec) | feat(release): add fail-closed qualification evaluator | [sase-1n6.5.1.1](sase-1n6.5.1.1.md) | 2026-10-19 21:09:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1n6.5.1.3][2] | Need evidence-phase CLI/JSON contract notes for CI reporting | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.3/README.md

<!-- sase:referenced-by:end -->
