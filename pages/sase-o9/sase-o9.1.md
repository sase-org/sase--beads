# Bead: sase-o9.1 — Observer carries the monitor's log path and agent name

[Bead Pages](../README.md) / [sase-o9](README.md) / sase-o9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md) · **Assignee:** `sase-o9.1` · **Size:** small
**Created:** 2026-08-17 06:54:27 EDT · **Closed:** 2026-08-17 07:15:51 EDT
**Plan:** [202608/procs\_tab\_monitor\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)

## Description

observer-monitor-fields: carry log_path and shell_name on ObservedProc and read a proc's tail from its own log path, so artifacts-owned monitor logs stream instead of reading empty.

## Notes

[2026-08-17T11:15:51Z · sase-o9.1] ObservedProc now carries log_path and shell_name from the durable Proc row; _read_log_tail forwards log_path so a selected monitor streams <artifacts_dir>/live_reply.md (including the rotated .1 sibling) while store-owned rows still read ~/.sase/procs/logs/<id>.log. Verified by tests: fields round-trip, a missing monitor log yields empty output, a monitor with no shell_name returns None from monitor_row_agent_name, and appending to the monitor log changes the published snapshot signature. just check passed (scoped lane escalated to the full suite because Justfile gained --epic-symbol sase-o9.2(monitor_row_agent_name) for the later presentation consumer).

[2026-08-17T11:16:42Z · sase-o9.1] ObservedProc now carries log_path and shell_name from the durable Proc row; _read_log_tail forwards log_path so a selected monitor streams <artifacts_dir>/live_reply.md (including the rotated .1 sibling) while store-owned rows still read ~/.sase/procs/logs/<id>.log. Verified by tests: fields round-trip, a missing monitor log yields empty output, a monitor with no shell_name returns None from monitor_row_agent_name, and appending to the monitor log changes the published snapshot signature. just check passed (scoped lane escalated to the full suite because Justfile gained --epic-symbol sase-o9.2(monitor_row_agent_name) for the later presentation consumer).

## Dependencies

- **Blocks:** [sase-o9.2](sase-o9.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o9.3](sase-o9.3.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o9.1/README.md) | [sase-o9.1](sase-o9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc80519`](https://github.com/sase-org/sase/commit/cc805197bc0314307190fcc1cf22725d0856f907) | feat(ace-tui): stream monitor proc tails from their own log path | [sase-o9.1](sase-o9.1.md) | 2026-08-17 07:17:43 EDT |
