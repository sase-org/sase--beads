# Bead: sase-m9.2.1.4 — Family-attached monitor facade and settlement

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.4` · **Size:** medium
**Created:** 2026-08-15 06:15:02 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

monitor-proc-facade: reimplement monitor start/list/show/stop as direct calls and projections over the shared proc service so one monitor has one proc id and no duplicate execution state or wrapper process. Compile the monitor command remainder to explicit [/bin/sh, -c, command] argv, attach a shell_kind=proc artifacts member to the target sase agent, preserve family allocation, status labels, workspace-claim transfer, bounded output, total/idle timeout, stop, and exactly-once --next behavior, and store immutable proc/artifacts cross-links. Correct required-option CLI-rule violations by using a command positional and optional policy defaults, retain hidden compatibility aliases/readers for historical monitor records, and never adopt a live legacy monitor. Cover starter death, launch failures, quiet and invalid-UTF8 output, background grandchildren, resistant process groups, claim transfer/release, and follow-up replay/suppression.

## Dependencies

- **Depends on:** [sase-m9.2.1.2](sase-m9.2.1.2.md) ◐ · ⧖ 2026-08-15
- **Depends on:** [sase-m9.2.1.3](sase-m9.2.1.3.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.5](sase-m9.2.1.5.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.4/README.md) | [sase-m9.2.1.4](sase-m9.2.1.4.md) | 0 |
