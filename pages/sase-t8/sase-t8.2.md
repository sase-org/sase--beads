# Bead: sase-t8.2 — Make implicit fork waits shell-aware

[Bead Pages](../README.md) / [sase-t8](README.md) / sase-t8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cz.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cz.f1.md) · **Assignee:** `sase-t8.2` · **Size:** medium
**Created:** 2026-08-24 18:28:19 EDT · **Closed:** 2026-08-24 20:17:15 EDT
**Plan:** [202608/fork\_every\_shell.md](https://github.com/sase-org/sase--plans/blob/main/202608/fork_every_shell.md)

## Description

shell-waits: bind exact proc identities and release deferred forks when agent, family, clan, or proc sources become terminal.

## Notes

[2026-08-24T23:03:30Z · 0d3] NOTE for sase-t8.2 worker: a small, standalone repair
(plan 202608/repair_failed_agent_fork_launch.md) just fixed a launch-boundary invariant
that this phase's shell-aware implicit-fork-wait work should preserve:
`bootstrap_agent_run()` in src/sase/axe/run_agent_runner_bootstrap.py must never treat
`SASE_AGENT_DEFERRED_WORKSPACE=1` combined with empty extracted wait metadata as a fatal
error. Launch preflight's cheap scan (`has_deferred_start_directive()`) is conservative
and cannot see that a named `#fork` parent has already gone terminal between preflight
and directive extraction; when extraction (or, going forward, your typed fork-dependency
resolution) legitimately drops an implicit wait for that reason, the run must still admit,
skip dependency-wait machinery, and let the post-admission launch phase
(`_prepare_workspace_and_repos()` in src/sase/axe/run_agent_runner_launch.py) claim a
real workspace via `claim_deferred_workspace()` before any model execution - it must
never fail in bootstrap and never execute the model in the workspace #0 placeholder.
If sase-t8.2 replaces the implicit-wait suppression path with a typed, terminal-aware
fork dependency, please keep or adapt the regressions in
tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py and
tests/test_axe_run_agent_failed_fork_admission.py rather than dropping the coverage.

[2026-08-25T00:16:43Z · sase-t8.2] PROPOSED FOLLOW-UP: Refresh generated memory README - just check currently fails at init memory --check because sase/memory/README.md is out of sync (+2 -2); not part of shell-aware fork waits.

[2026-08-25T00:17:15Z · sase-t8.2] Implemented shell-aware implicit fork waits; verified 101 touched tests passed and just check reached only unrelated init memory --check README drift, recorded as proposed follow-up; epic-symbols reported none.

[2026-08-25T00:24:34Z · sase-t8.2] POST-CLOSE UPDATE: Read resolved epic design and removed the old fork_parent_wait_is_unreachable shortcut/export so already-terminal fork parents now bind typed fork dependencies and release through the shared predicate; reverified 101 touched tests passed, just check passes all lint gates before the unrelated init memory --check README drift, and epic-symbols still reports none.

## Dependencies

- **Depends on:** [sase-t8.1](sase-t8.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-t8.3](sase-t8.3.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t8.2/README.md) | [sase-t8.2](sase-t8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a3e1d2`](https://github.com/sase-org/sase/commit/2a3e1d2c658bd6357bd71c8c8b91d4a56c4c65c2) | feat(agent): make implicit fork waits shell-aware | [sase-t8.2](sase-t8.2.md) | 2026-08-24 20:25:54 EDT |
