# Bead: sase-1tz.1.1.6 — Recover first, name unmeasured owners, and escalate missed recovery targets

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.6` · **Size:** medium
**Created:** 2026-11-19 07:28:42 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

pressure_recovery: the disk_pressure chop reaps before collecting a fail-open inventory. Its notice names unmeasured owners and uses an episode-scoped dedup key. A missed recovery target produces a distinct escalation with the target, reclaimed bytes, and blockers.

## Notes

[2026-11-19T14:50:39Z · sase-1tz.1.1.6] Apollo 2026-11-19 disk_pressure store: 99 rows (97 visible, 2 dismissed, 0 with a dedup_key). 62 lead with "Unattributed …"; newest (2026-11-16T21:06, fa2a3f88) leads with "Unattributed 192.7 GiB on the SASE_HOME filesystem". After-install repeat: ssh apollo -- sase notify list --sender disk_pressure --all --json --limit 10000

## Dependencies

- **Depends on:** [sase-1tz.1.1.1](sase-1tz.1.1.1.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.1.1.4](sase-1tz.1.1.4.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md) | [sase-1tz.1.1.6](sase-1tz.1.1.6.md) | 0 |
