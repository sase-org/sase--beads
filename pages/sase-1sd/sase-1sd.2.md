# Bead: sase-1sd.2 — Stop runner module imports from replacing the process SIGTERM handler (sase-1s2)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.2` · **Size:** small
**Created:** 2026-11-12 05:26:15 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

sigterm-import: importing sase.axe.run_agent_runner (line 87) or sase.axe.mentor_runner (line 30) installs a soft SIGTERM handler at import time, replacing the caller's handler in every importer (pytest workers, tool runs). Move the install into the runner-owned entry lifecycle, keeping production shutdown semantics, and add fresh-interpreter import plus real-entry signal tests.

## Notes

[2026-11-12T11:34:28Z · sase-1sd.2] TASK RESOLVED: sase-1s2 — fresh-interpreter imports of sase.axe.run_agent_runner and sase.axe.mentor_runner leave the caller SIGTERM handler in place (athena, base e072729599; before: SIG_DFL became install_sigterm_handler._handler; after: caller handler preserved). Agent main() still installs soft=True and settles under a real SIGTERM; mentor main() still installs the hard handler and exits 128+SIGTERM. Coverage: tests/axe/test_runner_import_sigterm.py plus tests/test_axe_runner_utils_signals.py (14 passed) and runner main/bootstrap tests (25 passed). No sase-1ra members were live on this surface. Bootstrap still reinstalls the workspace-release handler.

## Dependencies

- **Depends on:** [sase-1sd.1](sase-1sd.1.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.3](sase-1sd.3.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.2.md) | [sase-1sd.2](sase-1sd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`063c982`](https://github.com/sase-org/sase/commit/063c98293b69f23543c91d66709a2b28eaa310a1) | fix(axe): install SIGTERM handlers in runner main, not at import | [sase-1sd.2](sase-1sd.2.md) | 2026-11-12 06:59:06 EST |
