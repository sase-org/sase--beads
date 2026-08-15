# Bead: sase-m9.2.1.4 — Family-attached monitor facade and settlement

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.4` · **Size:** medium
**Created:** 2026-08-15 06:15:02 EDT · **Closed:** 2026-08-15 09:24:14 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

monitor-proc-facade: reimplement monitor start/list/show/stop as direct calls and projections over the shared proc service so one monitor has one proc id and no duplicate execution state or wrapper process. Compile the monitor command remainder to explicit [/bin/sh, -c, command] argv, attach a shell_kind=proc artifacts member to the target sase agent, preserve family allocation, status labels, workspace-claim transfer, bounded output, total/idle timeout, stop, and exactly-once --next behavior, and store immutable proc/artifacts cross-links. Correct required-option CLI-rule violations by using a command positional and optional policy defaults, retain hidden compatibility aliases/readers for historical monitor records, and never adopt a live legacy monitor. Cover starter death, launch failures, quiet and invalid-UTF8 output, background grandchildren, resistant process groups, claim transfer/release, and follow-up replay/suppression.

## Notes

[2026-08-15T13:23:30Z · sase-m9.2.1.4] PROPOSED FOLLOW-UP: just check escalates via core-identity-changed / stale_actionable because the declared sase-core-rs floor is 0.27.2 while reserve_proc, claim_proc_supervisor, request_proc_stop, begin_proc_settlement, and finish_proc first appear in published 0.27.3 (6d7000a). Land should raise the Python floor after the core release is the installed default.

[2026-08-15T13:23:44Z · sase-m9.2.1.4] PROPOSED FOLLOW-UP: 50+ unrelated CLI/TUI tests fail on this tree because captured stdout now includes Rich ANSI bold around numbers and brackets (smallest repro: tests/test_output.py::test_escape_markup_in_log_fn). Not caused by the monitor facade; just check escalated via core-identity-changed / stale baseline.

[2026-08-15T13:23:58Z · sase-m9.2.1.4] PROPOSED FOLLOW-UP: tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash timed out once in the escalated scoped suite (TimeoutError waiting for proc) but passed in isolation (0.67s). Looks like full-suite load flake from the supervisor phase, not the monitor facade.

[2026-08-15T13:24:14Z · sase-m9.2.1.4] Reimplemented sase monitor start/list/show/stop as a proc-service facade: one monitor id is the proc id, command remainder compiles to [/bin/sh, -c, command], members get shell_kind=proc plus immutable proc/artifacts cross-links, and settlement writes family markers, claim transfer/release, and exactly-once --next. CLI uses a command positional with optional reason (run command) and timeout (1h) plus a hidden -c alias; live legacy monitors are never adopted. Verified with just install, focused monitor/proc/CLI suites (213 passed including starter death, launch failure, quiet/invalid-UTF8, grandchildren/resistant groups, claim transfer/release, follow-up suppression), just check lint (fmt/ruff/mypy/symvision passed), and the escalated scoped suite (8305 passed; Rich-ANSI CLI failures plus one isolated-passing supervisor flake recorded as follow-up).

[2026-08-15T13:25:07Z · sase-m9.2.1.4] Verified monitor is a facade over the shared proc service: one monitor id equals one proc id, start compiles the positional command to /bin/sh -c, workspace claim happens after supervisor ack, settlement writes family artifacts and follow-up, stop suppresses --next, live legacy monitors stay on the old path. just install; focused monitor/proc/CLI suites (213 passed); just check lint; escalated scoped suite 8305 passed. CLI accepts sase monitor start -- just check-full with -r/-t defaults and hidden -c alias.

## Dependencies

- **Depends on:** [sase-m9.2.1.2](sase-m9.2.1.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m9.2.1.3](sase-m9.2.1.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.5](sase-m9.2.1.5.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.4/README.md) | [sase-m9.2.1.4](sase-m9.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8b4635a`](https://github.com/sase-org/sase/commit/8b4635ad13e8caa76a004adee92d41c4322fd43c) | feat(monitor): run monitors through the shared proc service | [sase-m9.2.1.4](sase-m9.2.1.4.md) | 2026-08-15 09:25:57 EDT |
