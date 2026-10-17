# Bead: sase-1lh.7.5.2 — Reconcile current release-blocking tests, docs anchors, and four visual diffs

[Bead Pages](../README.md) / [sase-1lh.7.5](sase-1lh.7.5.md) / sase-1lh.7.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.land.md) · **Assignee:** `sase-1lh.7.5.2` · **Size:** medium
**Created:** 2026-10-16 20:23:09 EDT · **Closed:** 2026-10-16 22:06:52 EDT
**Plan:** [202610/finish\_recapture\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_recapture_release.md)

## Description

release-integration: integrate the launch submission timestamp and logical-plan repair changes with their audits, reconcile docs-owned gate drift, inspect and repair the four persistent visual differences, and verify the release floor contract.

## Notes

[2026-10-17T00:27:45Z · toobig-82.test_agent_display_clan_hints.0] DISCOVERED ISSUE: Independent scoped-check reproduction of the launch-approval extra_env stub gap already tracked as sase-1lw. sase tool run 32d89874e9bc6457ec121619049299f8 failed tests/test_launch_approval_tui.py::test_tui_launch_approval_dispatch_failure_records_failed_response (NEW) and tests/test_launch_approval.py::test_approve_launch_response_dispatches_stored_request because fake_launch does not accept extra_env now passed by launch_request_response.py. This phase already owns integrating the launch submission timestamp with its audits; corroborated sase-1lw rather than filing a new task.

[2026-10-17T02:06:42Z · sase-1lh.7.5.2] PROPOSED FOLLOW-UP: Remove epic/phase-label mentions from the seven hand-written Reference locations reported by tools/check_docs (reference/agents/initialization.md:121; reference/agents/memory-initialization.md:36,91,241; reference/config/core-behavior.md:262; reference/memory/memory.md:172; reference/providers/agent-clis.md:484). No matching task bead was found. The identical seven E5 errors reproduce from a clean git archive of starting HEAD 499c825cb9, so this does not block this phase. Verified the project-label audit exemption, launch submission timestamp transport assertions, root help text, and four inspected screenshot updates. Focused suites passed (44 and 34 tests), docs-check passed with 3140 URLs, the release contract set passed (832 tests), and both TZ=UTC targeted screenshot proofs passed with unchanged=4 and zero unstable nodes. just fix passed. sase tool run check passed formatting and all lint stages except docs contract, which has only the clean-base E5 errors above. Independent retry-ID reproduction was recorded on existing task sase-173.

[2026-10-17T02:06:52Z · sase-1lh.7.5.2] Reconciled the launch/audit/help regressions and four inspected screenshot diffs. just fix passed; focused suites (44 and 34 tests), docs-check (3140 URLs), release contract set (832 tests), and two TZ=UTC screenshot proofs passed. sase tool run check reached only the seven E5 docs-contract errors, reproduced identically from clean HEAD 499c825cb9 and recorded as a proposed follow-up. epic-symbols reported no leftovers; retry screenshot evidence was added to existing task sase-173.

## Dependencies

- **Depends on:** [sase-1lh.7.5.1](sase-1lh.7.5.1.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1lh.7.5.3](sase-1lh.7.5.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.2/README.md) | [sase-1lh.7.5.2](sase-1lh.7.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f564f0f`](https://github.com/sase-org/sase/commit/f564f0f9962384f9aa05e8d2b1be02e54e413698) | test(release): reconcile launch, docs, and visual regressions | [sase-1lh.7.5.2](sase-1lh.7.5.2.md) | 2026-10-16 22:07:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:toobig-82.test_agent_display_clan_hints.0][2] | Need phase scope before recording extra_env launch-approval evidence on the active epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-82.test_agent_display_clan_hints.0/README.md

<!-- sase:referenced-by:end -->
