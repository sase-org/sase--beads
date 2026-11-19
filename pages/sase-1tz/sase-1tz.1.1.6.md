# Bead: sase-1tz.1.1.6 — Recover first, name unmeasured owners, and escalate missed recovery targets

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.6` · **Size:** medium
**Created:** 2026-11-19 07:28:42 EST · **Closed:** 2026-11-19 10:24:10 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

pressure_recovery: the disk_pressure chop reaps before collecting a fail-open inventory. Its notice names unmeasured owners and uses an episode-scoped dedup key. A missed recovery target produces a distinct escalation with the target, reclaimed bytes, and blockers.

## Notes

[2026-11-19T14:50:39Z · sase-1tz.1.1.6] Apollo 2026-11-19 disk_pressure store: 99 rows (97 visible, 2 dismissed, 0 with a dedup_key). 62 lead with "Unattributed …"; newest (2026-11-16T21:06, fa2a3f88) leads with "Unattributed 192.7 GiB on the SASE_HOME filesystem". After-install repeat: ssh apollo -- sase notify list --sender disk_pressure --all --json --limit 10000

[2026-11-19T15:24:10Z · sase-1tz.1.1.6] Verified: disk_pressure reaps before a 20s fail-open inventory; notices lead with free space/recovery, name unmeasured owners, and use episode-scoped keys; missed targets upsert a distinct escalation and set check_error (recovery_missed/recovery_blocked). managed_tmp_reap and sase disk reap never collect inventory. 23 focused tests plus sase tool run check (b16fd7d9) passed. Apollo 2026-11-19: 99 disk_pressure rows (97 visible, 0 dedup keys). Coordination notes on sase-zw.8, sase-11h, sase-1tz.1. No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-1tz.1.1.1](sase-1tz.1.1.1.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.1.1.4](sase-1tz.1.1.4.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md) | [sase-1tz.1.1.6](sase-1tz.1.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7b6a44a`](https://github.com/sase-org/sase/commit/7b6a44a100e5090d8cc98481377d01af40c54aca) | feat(disk): recover under pressure before attributing owners | [sase-1tz.1.1.6](sase-1tz.1.1.6.md) | 2026-11-19 10:26:11 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.6][1] | Confirm the apollo measurement note landed after the unpublished-commit warning | 6 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md

<!-- sase:referenced-by:end -->
