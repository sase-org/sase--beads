# Bead: sase-11r.3 — Stop monitor start from destroying command quoting

[Bead Pages](../README.md) / [sase-11r](README.md) / sase-11r.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lx.md) · **Assignee:** `sase-11r.3` · **Size:** small
**Created:** 2026-09-16 10:07:20 EDT · **Closed:** 2026-09-16 10:46:10 EDT
**Plan:** [202609/monitor\_verify\_handoff\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_verify_handoff_hardening.md)

## Description

argv-quoting: preserve remainder argv with shlex-aware joining, warn on redundant bash -c wrappers, and update the monitor skill's command-authoring guidance.

## Notes

[2026-09-16T14:46:10Z · sase-11r.3] Fixed start_command in src/sase/main/monitor/common.py: single-word remainder returned verbatim, multi-word remainder joined with shlex.join (was a naive ' '.join that destroyed inner quoting, e.g. turning 'bash -c just install && just check' -- exactly the sase-11o.1 incident bug). Added a stderr-only warning in start.py when the resolved command starts with bash -c/sh -c, flagging the wrapper as redundant since the host already runs under /bin/sh -c. Updated the sase_monitor skill source (Hazards section) to document argv-for-argument preservation and warn against bash -c wrappers. Added tests/main/test_monitor_start_command.py (unit tests for the three shapes: bare words, single quoted string, bash -c wrapper) and an e2e test in tests/main/test_monitor_handler_start_launch.py asserting the stored monitor_command preserves inner quoting and the warning fires. Verified: sase bead epic-symbols sase-11r.3 has no leftover entries; ran just install (stale rust wheel in this workspace) then just check clean (all lint gates + 95/3918 scoped test files, no failures), including the new tests.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11r.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11r.3/README.md) | [sase-11r.3](sase-11r.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a36ff57`](https://github.com/sase-org/sase/commit/a36ff57c9d462edc77d000938724053459f9e529) | fix(monitor): stop monitor start from destroying command quoting | [sase-11r.3](sase-11r.3.md) | 2026-09-16 10:47:17 EDT |
