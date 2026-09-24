# Bead: sase-17p.3 — Reserve the ToolRun when a monitor start hands off a tool run

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.3` · **Size:** medium
**Created:** 2026-09-24 08:40:22 EDT · **Closed:** 2026-09-24 12:00:31 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

monitor-handoff: when a monitor's proc will run a ToolRun, reserve and bind it to the monitor before hand-off and run the adopting worker, leaving monitor_command, execution_argv, and -f bindings untouched, fail-open to E1.5 wrapping, behind the same flag.

## Notes

[2026-09-24T16:00:31Z · sase-17p.3] Monitor-start ToolRun reservation landed behind tool_handoff: named/explicit/ad-hoc wraps reserve a monitor-owned created run and exec the _adopt worker (proc argv + tool-run tags, parent markers cleared), monitor_command/execution_argv and -f completion path untouched, fail-open to E1.5 with a one-line log reason on reservation failure, launch_failed settlement on post-reservation submit failure, run id in start output/JSON, monitor show/detail, and follow-up prompt. Verified: 21 new tests in tests/monitor/test_monitor_tool_handoff.py plus all 24 existing E1.5 wrap tests pass; 83 pass across monitor models/followup/start, wire mirrors, and phase-2 handoff suites; ruff, ruff format, and mypy clean; symvision output byte-identical to base; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-17p.2](sase-17p.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.5](sase-17p.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.3/README.md) | [sase-17p.3](sase-17p.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7f450e0`](https://github.com/sase-org/sase/commit/7f450e0112d43136cf19afde6053979747c43439) | feat(monitor): reserve ToolRun hand-off on monitor start (sase-17p.3) | [sase-17p.3](sase-17p.3.md) | 2026-09-24 12:02:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.3.1.land][1] | Check phase notes for already-recorded fakey color / completion snapshot / parser tool / monitor start policy failures | 1 |
| read-by | [agent:sase-17p.3][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17p.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.land/README.md

<!-- sase:referenced-by:end -->
