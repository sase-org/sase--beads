# Bead: sase-1ra.3 — Pytest isolation: scrub SASE\_MODEL\_OVERRIDE and O(1) per-test homes (sase-1q3, sase-1qe)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.3` · **Size:** small
**Created:** 2026-11-04 17:59:13 EST · **Closed:** 2026-11-04 18:29:59 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

pytest_env: add SASE_MODEL_OVERRIDE to the autouse env scrub and replace the per-test mktemp home allocation with a per-worker parent plus mkdtemp, both in tests/_conftest_environment.py (sase-1q3, sase-1qe).

## Notes

[2026-11-04T23:29:53Z · sase-1ra.3] PROPOSED FOLLOW-UP: Reconcile existing check triage for tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms (KNOWN) and tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed (FLAKY); ToolRun 184981c168d86e595070aa89bb854b6f reported no_new_failures.

[2026-11-04T23:29:59Z · sase-1ra.3] Added SASE_MODEL_OVERRIDE to per-test ambient env cleanup and changed isolated homes to mkdtemp directories under the pytest worker temp parent. just fix passed; sase tool run check passed all lint stages and triaged the scoped lane as no_new_failures (one KNOWN and one FLAKY test). git diff --check passed; epic-symbol check found no remaining entries.

## Dependencies

- **Blocks:** [sase-1ra.4](sase-1ra.4.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.3/README.md) | [sase-1ra.3](sase-1ra.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`394ff93`](https://github.com/sase-org/sase/commit/394ff93ff5f35944596e349dee3e274d5290c083) | test(pytest): isolate per-test SASE homes | [sase-1ra.3](sase-1ra.3.md) | 2026-11-04 18:31:45 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ra.3][1] | Confirm the assigned phase was closed after the verification note | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.3/README.md

<!-- sase:referenced-by:end -->
