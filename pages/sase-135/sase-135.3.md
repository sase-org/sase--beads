# Bead: sase-135.3 — Execute and inspect foreground runs reliably

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.3` · **Size:** medium
**Created:** 2026-09-18 22:19:20 EDT · **Closed:** 2026-09-19 08:19:54 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

foreground-run: Implement section 3, including exact argv, two-stream output, signals, fail-open recording, ownership and bounded logs, lost-run recovery, runs/show queries, and real-process acceptance cases.

## Notes

[2026-09-19T12:19:54Z · sase-135.3] Implemented foreground ToolRun execution: sase tool run/runs/show, two-stream pumps, signal forwarding, fail-open recording, parent/enclosing ownership, lost-run reconciliation, and retained-log replay.

DEMO: sase tool run -- sh -c 'printf out; printf err >&2; exit 3' -> stdout exactly out, stderr has err plus wrapper metadata, exit 3; show -j reports failed/3 with retained-log metadata.
DEMO: tools/smoke_sase_tool_runs --sase .venv/bin/sase -> dod-2-exact-execution, dod-2-literal-argv, dod-3-signals (143/signaled, 130/interrupted), dod-4-lost (runner exited without settling, no guessed duration/exit), dod-5-fail-open (printf hi, exit 0, run not recorded), dod-5-running-before-spawn, dod-7-agent-output, dod-8-enclosing-owner all pass; live-owner remains phase-pending.
DEMO: sase bead epic-symbols sase-135.3 -> no leftovers. Re-keyed unused tool_run_append_event to sase-135.4.

Verified: just check passed (full suite after Justfile epic-symbol re-key). Compact root help still omits tool (phase 6).

## Dependencies

- **Depends on:** [sase-135.2](sase-135.2.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-135.4](sase-135.4.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.3/README.md) | [sase-135.3](sase-135.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`91b6767`](https://github.com/sase-org/sase/commit/91b67672b4f23dfb4f8eae10394de46195edd24f) | feat(cli): add foreground ToolRun execution and run/runs/show | [sase-135.3](sase-135.3.md) | 2026-09-19 08:23:04 EDT |
