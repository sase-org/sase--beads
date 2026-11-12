# Bead: sase-1sd.2 — Stop runner module imports from replacing the process SIGTERM handler (sase-1s2)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.2` · **Size:** small
**Created:** 2026-11-12 05:26:15 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

sigterm-import: importing sase.axe.run_agent_runner (line 87) or sase.axe.mentor_runner (line 30) installs a soft SIGTERM handler at import time, replacing the caller's handler in every importer (pytest workers, tool runs). Move the install into the runner-owned entry lifecycle, keeping production shutdown semantics, and add fresh-interpreter import plus real-entry signal tests.

## Dependencies

- **Depends on:** [sase-1sd.1](sase-1sd.1.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.3](sase-1sd.3.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.2/README.md) | [sase-1sd.2](sase-1sd.2.md) | 0 |
