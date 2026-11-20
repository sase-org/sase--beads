# Bead: sase-1tz.4.1.12 — Apply the tool-run log horizon on a schedule, age-rotate tui.log, and verify digest and run pruning

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.12` · **Size:** medium
**Created:** 2026-11-20 14:00:25 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

log_horizons: an hourly housekeeping chop applies the existing tool-run retention owner, not only under disk pressure, and removes emptied run dirs. tui.log rotates by age as well as size. Verify error-digest pruning and that artifact_run_prune is unblocked on both hosts.

## Dependencies

- **Blocks:** [sase-1tz.4.1.13](sase-1tz.4.1.13.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.12/README.md) | [sase-1tz.4.1.12](sase-1tz.4.1.12.md) | 0 |
