# Bead: sase-p3.12 — The \`github\` task type and mirror wiring

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.12` · **Size:** small
**Created:** 2026-08-17 18:50:07 EDT · **Closed:** 2026-08-18 00:59:21 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

github-type: register the agent-uncreatable `github` task type from the sase-github plugin and have the external issue mirror stamp it.

## Notes

[2026-08-18T04:58:26Z · sase-p3.12] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-pa with no definition for key epic_resume_gate — pre-existing, not caused by this phase

[2026-08-18T04:58:41Z · sase-p3.12] PROPOSED FOLLOW-UP: sase memory init --check fails on home chezmoi memory by re-adding File Discovered Work As Task Beads to sase.md/AGENTS.md — pre-existing template/home drift, not caused by this phase

[2026-08-18T04:58:57Z · sase-p3.12] PROPOSED FOLLOW-UP: tests/test_procs_supervisor.py::test_process_group_kill_reaps_grandchildren_and_resistant_children failed once in the escalated suite with ValueError empty int, then passed on rerun — flaky, not caused by this phase

[2026-08-18T04:59:21Z · sase-p3.12] Registered sase-github sase_task_types spec github (agent_creatable=false, glyph ⑂, accent #B2B2B2, no extra fields). Issue mirror stamps task_type=github on new creates and fails closed with the plugins.required install message if the type is absent; existing untyped mirrored beads are not backfilled. Verified live registry includes github from the linked plugin; sase-github task-type tests (4) passed; mirror create/status/required-plugin tests passed; fixed test_unknown_type_renders_degraded_key_values to isolate the unknown-catalog case. sase bead epic-symbols sase-p3.12 reported no leftovers. just check lint (ruff/mypy/symvision/fmt) passed; full escalated suite 32982 passed after the render-test fix. Did not close parent epic sase-p3.

[2026-08-18T05:00:30Z · sase-p3.12] github task type registered in sase-github (agent_creatable=false); apply_issue_mirror stamps task_type=github on new mirrored beads and fail-closes with the plugins.required install message when github is missing; existing untyped mirrored beads still reconcile; epic-symbols clean

## Dependencies

- **Blocks:** [sase-p3.13](sase-p3.13.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.5](sase-p3.5.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.12/README.md) | [sase-p3.12](sase-p3.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`118a608`](https://github.com/sase-org/sase/commit/118a60836905cf08c8f226c610b6acec2e834880) | feat(external-mirror): stamp github task type on new mirrored issues | [sase-p3.12](sase-p3.12.md) | 2026-08-18 01:01:18 EDT |
