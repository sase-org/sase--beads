# Bead: sase-1n6.5.1.3 — Run reusable CI at an explicit ref and report qualification evidence

[Bead Pages](../README.md) / [sase-1n6.5.1](sase-1n6.5.1.md) / sase-1n6.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) · **Assignee:** `sase-1n6.5.1.3` · **Size:** medium
**Created:** 2026-10-19 20:21:19 EDT · **Closed:** 2026-10-19 23:34:18 EDT
**Plan:** [202610/published\_core\_qualification.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md)

## Description

ci-evidence: thread qualification inputs and concurrency through ci.yml, collect real pytest evidence without changing test commands, and retain job diagnostics.

## Notes

[2026-10-20T03:34:05Z · sase-1n6.5.1.3] CLI/JSON contract for qualification evidence (for release-wiring and later evaluators):

Plugin: opt-in only via PYTEST_ADDOPTS='-p tests._pytest_qualify_evidence' plus SASE_QUALIFY_EVIDENCE_PATH. Lives at tests/_pytest_qualify_evidence.py so CI does not set PYTHONPATH to the repo root. xdist workers are detected via config.workerinput (not inherited PYTEST_XDIST_WORKER). Nested pytest cannot overwrite the outer report (O_EXCL .owner claim). Session file kind=pytest_session schema_version=1 with collected/passed/failed/errors/skipped/collection_failed/exit_status/first_failing_node_ids/flaky_lines.

Writer: stdlib tools/write_qualification_evidence. Modes: --print-inventory-digest; --bind-manifest PATH --expected-core-version V --github-output FILE (writes candidate-id and generation, refuses core_version mismatch); --kind pytest|command --out PATH (writes identity-bound evidence). Payload filenames stay qualify-evidence-<job>.json; artifact names are qualify-evidence-lint-attempt-${{ github.run_attempt }} and qualify-evidence-test-<py>-attempt-${{ github.run_attempt }}. Missing/unreadable pytest session => kind=pytest invalid=true with diagnostics (never fabricated green). Lint is kind=command with steps[] and missing_bindings[] parsed from check_sase_core_rs_bindings stderr. Binding fields: repository, candidate_id, generation, checked_out_sha, expected_core_version, installed_core_version, inventory_digest, workflow_run_id, job_id, job_name, attempt.

ci.yml: workflow_call inputs ref/core-source(default source)/core-version/manifest-artifact(default candidate-build)/probe-core-version. Concurrency qualify-<sha> cancel-in-progress=false when inputs.ref is set; ordinary CI keeps ci-<ref> cancellation. Use inputs.ref truthiness (inputs.ref != '' is true when inputs is null on pull_request). Test commands remain just test-cov / just test.

[2026-10-20T03:34:18Z · sase-1n6.5.1.3] ci-evidence: reusable CI accepts ref/core-source/core-version/manifest-artifact/probe-core-version, pins qualify-<sha> without cancel, threads ref and expected-core-version, and writes identity-bound lint/test evidence on always() including invalid pytest when the session is missing. Opt-in plugin tests/_pytest_qualify_evidence.py plus stdlib tools/write_qualification_evidence; test commands stay just test-cov/just test. Verified: 79 focused tests under xdist including pass/fail/collection/zero/setup/nested/xdist/FLAKY/inherited-worker-env; sase tool run check 84e9332a35f3ad88e04302bbac168ba3 green; no --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1n6.5.1.2](sase-1n6.5.1.2.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.5.1.4](sase-1n6.5.1.4.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.3/README.md) | [sase-1n6.5.1.3](sase-1n6.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8afb1b7`](https://github.com/sase-org/sase/commit/8afb1b7e57e4e3494074a73adde2d3cee2fa5148) | feat(ci): collect identity-bound qualification evidence from reusable CI | [sase-1n6.5.1.3](sase-1n6.5.1.3.md) | 2026-10-19 23:35:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.3][1] | Need the phase scope and design file | 5 |
| read-by | [agent:sase-1n6.5.1.4][2] | Need sibling phase contracts for release-wiring | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md

<!-- sase:referenced-by:end -->
