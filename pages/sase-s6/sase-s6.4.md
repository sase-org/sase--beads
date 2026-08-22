# Bead: sase-s6.4 — Sandboxed conditional admission runtime

[Bead Pages](../README.md) / [sase-s6](README.md) / sase-s6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0b8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0b8.md) · **Assignee:** `sase-s6.4` · **Size:** medium
**Created:** 2026-08-22 18:14:59 UTC · **Closed:** 2026-08-22 22:38:35 UTC
**Plan:** [202608/typed\_launch\_units.md](https://github.com/sase-org/sase--plans/blob/main/202608/typed_launch_units.md)

## Description

conditional-runtime: evaluate approved Bash or Python %if programs with bounded resources and typed context, and settle false predicates as durable skipped outcomes without allocating an agent, proc, workspace, or runner.

## Notes

[2026-08-22T22:38:35Z · sase-s6.4] Implemented sandboxed %if evaluator around CodeValue: private 0600 scripts, argv without interpolation, sanitized env, versioned SASE_CONDITION_CONTEXT, process-group timeout/output caps, exit 0 eligible / 1 skipped / other condition-error. Coordinator recovers proven result.json without re-running and skip/error allocate no runner/workspace. LaunchConditionWire is consumed; Justfile --epic-symbol sase-s6.4 removed. Verified cargo clippy (sase-core workspace), sase_core condition tests, pytest tests/test_launch_condition_runtime.py + tests/test_launch_admission.py, just check (lint+scoped full-suite escalation), and sase bead epic-symbols sase-s6.4 with no leftovers.

## Dependencies

- **Depends on:** [sase-s6.3](sase-s6.3.md) ✓ · ⧖ 2026-08-22
- **Blocks:** [sase-s6.5](sase-s6.5.md) ✓ · ⧖ 2026-08-22
- **Blocks:** [sase-s6.8](sase-s6.8.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.4/README.md) | [sase-s6.4](sase-s6.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13266fd`](https://github.com/sase-org/sase/commit/13266fdcaea9f420917478ced04a12d072036246) | feat(agent-launch): evaluate sandboxed %if admission predicates | [sase-s6.4](sase-s6.4.md) | 2026-08-22 22:39:53 UTC |
| sase-core | [`sase-core@e950120`](https://github.com/sase-org/sase-core/commit/e950120d8452608440028025f61c298d928c0cec) | feat(agent-launch): add sandboxed %if condition evaluator | [sase-s6.4](sase-s6.4.md) | 2026-08-22 22:44:01 UTC |
