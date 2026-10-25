# Bead: sase-1n6.6 — Digest-checked publish, PyPI confirmation, and un-draft

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.6` · **Size:** medium
**Created:** 2026-10-19 16:40:09 EDT · **Closed:** 2026-10-25 16:41:25 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

publish: release.yml uploads only missing files after digest checks, confirms every file and an exact install from PyPI, runs the family canary, then un-drafts; a resume mode re-enters at publish.

## Notes

[2026-10-25T19:59:47Z · sase-1n6.6] Live proof (local, read-only): real uv build of master 0.18.1 sealed with live sase-core-rs==0.42.6 file set; publish-plan vs live PyPI exits 2 with PUBLISH_CONFLICT for every file (different SHA-256), and confirm vs live PyPI exits 2 with PUBLISH_CONFLICT, refusing without un-drafting. Matches the plan rehearsal expectation. Full rehearse dispatch deferred: it would run pre-land master workflow files without these jobs, so the green-rehearsal proof belongs to the land agent after landing. just check joined as ToolRun 29efcce1e1422d944f63e93fcaf0fe88.

[2026-10-25T20:41:25Z · sase-1n6.6--1] Fixed contract-set budget for publish guard: bumped cap 87->88 with measured 144.73s across 88 entries (1064 passed). Prior ToolRun 29efcce1e1422d944f63e93fcaf0fe88 was red only on test_contract_set_manifest_entry_budget_has_no_hidden_headroom (88 vs 87, overflow tests/test_validate_test_environment_tool.py); root cause was the new tests/test_release_candidate_publish.py contract guard added by this phase. Verified: tests/test_contract_manifest.py 3 passed, full 88-entry contract set 1064 passed in 144.73s, publish+release focused 39 passed. epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1n6.5](sase-1n6.5.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.9](sase-1n6.9.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.6.md) | [sase-1n6.6](sase-1n6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d1a04e6`](https://github.com/sase-org/sase/commit/d1a04e62509793813d0c352e27db6698a334ed48) | feat(release): digest-checked publish with PyPI confirm and contract budget 88 | [sase-1n6.6](sase-1n6.6.md) | 2026-10-25 16:42:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13d][1] | Research which agents stalled the sase-1n6 epic: in-progress phases | 1 |
| read-by | [agent:research.2a.cld][2] | E3 readiness: E2 status | 1 |
| read-by | [agent:research.2a.grk][3] | Need remaining open E2 phase statuses and blockers before designing E3 | 1 |
| read-by | [agent:research.2a.mus][4] | E3 readiness: remaining E2 phases status | 1 |
| read-by | [agent:sase-1n6.5.1.4][5] | Need the publish-phase contract that consumes qualify verdict | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13d/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.grk/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.mus/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md

<!-- sase:referenced-by:end -->
