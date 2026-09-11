# Bead: sase-yy.8.5 — Verify real producer, crash, and reconciliation paths end to end

[Bead Pages](../README.md) / [sase-yy.8](sase-yy.8.md) / sase-yy.8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.5` · **Size:** medium
**Created:** 2026-09-10 14:27:28 EDT · **Closed:** 2026-09-10 20:27:14 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

acceptance: extend multi-clone tests through production producers and actual process death, cover every reproduced landing defect and public mutation path, and complete the existing flag-retirement verification.

## Notes

[2026-09-11T00:20:26Z · sase-yy.8.5] PROPOSED FOLLOW-UP: tests/fakey/test_provider_drain_e2e.py:65,86 fail the just check "test waits" lint gate (fixed-sleep-missing-pragma) on current master HEAD, unrelated to this phase. Pre-existing since commit 63a5dbef1 (fix(agent): repair provider drain forced-reuse relaunches); the check_test_wait_helpers gate was widened by c49452c47 around the same time and this file was never updated. Fix: add an inline `# sase-test-wait: <reason>` pragma to the two time.sleep(0.01) polling calls in _wait_for_file/_wait_for_json (they are already observable-condition polls, just missing the pragma), or migrate to a shared wait helper.

[2026-09-11T00:20:55Z · sase-yy.8.5] PROPOSED FOLLOW-UP: src/sase/ace/tui/models/agent_live_query.py fails the just check "symvision" lint gate (unused public functions agent_live_query_entry and agent_live_query_row_id) on current master HEAD, unrelated to this phase. Pre-existing since commit bfcdc0416 (feat(query): add agents-live profile adapter). Fix: either make these functions private if only used within the file, delete them if genuinely unused, or wire up their real callers.

[2026-09-11T00:27:14Z · sase-yy.8.5--1] Verified: just check-full's only failure is the pre-existing test-waits lint gate on tests/fakey/test_provider_drain_e2e.py:65,86 (commit 63a5dbef1c, predates this phase — confirmed via git status/blame, untouched by this phase's diff), already logged as PROPOSED FOLLOW-UP note #1. No new or artifact-link-related failures found. epic-symbols empty. Direct pytest runs (339 tests across tests/sdd/, test_artifact_link_outbox.py, test_artifact_cli_link.py, test_plan_command_handler_metadata.py) covering the process-death, mutation-path, cutover-resume, and outbox-drain regression tests all passed. Flag bead sase-z0 (link_events) already closed.

## Dependencies

- **Depends on:** [sase-yy.8.1](sase-yy.8.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-yy.8.2](sase-yy.8.2.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-yy.8.3](sase-yy.8.3.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-yy.8.4](sase-yy.8.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.5.md) | [sase-yy.8.5](sase-yy.8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8eabf9e`](https://github.com/sase-org/sase/commit/8eabf9ecf82518d960cadb41f9cc17318e6d6558) | test(artifact-links): cover process death, mutation isolation, and cutover resume | [sase-yy.8.5](sase-yy.8.5.md) | 2026-09-10 20:28:17 EDT |
