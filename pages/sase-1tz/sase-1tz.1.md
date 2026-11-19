# Bead: sase-1tz.1 — Honest disk attribution and the held-workspace re-settlement loop (items 1-2)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.1` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

outage: stop reporting unmeasured disk as 0 B/complete, measure workspace roots first, run reaping independently of inventory completeness, and make pressure notices name unmeasured owners and escalate missed recovery targets. Settle held workspaces once per evidence fingerprint, +1 only when evidence changes, and add a sase-core store guard that coalesces +1s and never rewrites the store for dismissed rows.

## Notes

[2026-11-19T13:20:31Z · sase-1tz.1.1.7] standing_skips: measured 34 athena managed_tmp_reap skip warnings on 2026-11-19 so far; after-install repeat command and implementation result are recorded on sase-1tz.1.1.7.

[2026-11-19T14:49:24Z · sase-1tz.1.1.5] owner_first: workspace and owner roots now get a separate 90s pass with 60s per root and four concurrent du processes before detail and stray scans; read-only Apollo/Athena baselines and the expected per-root du tolerance are on sase-1tz.1.1.5, with post-install comparison pending the human-owned install.

[2026-11-19T14:50:49Z · sase-1tz.1.1.6] pressure_recovery: apollo 99 disk_pressure rows (97 visible, 0 dedup keys) as of 2026-11-19; after-install ssh apollo -- sase notify list --sender disk_pressure --all --json --limit 10000

[2026-11-19T14:57:01Z · sase-1tz.1.1.2] held_settle (sase-1tz.1.1.2) measurement: athena store generation advanced ~20/min on a 7.3 MB file before the fix (2026-11-19 09:04 EST); after-install repeat: g1=$(cat ~/.sase/notifications/notifications.jsonl.generation); sleep 60; g2=$(cat ~/.sase/notifications/notifications.jsonl.generation); echo $((g2-g1)).

## Dependencies

- **Blocks:** [sase-1tz.2](sase-1tz.2.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) | [sase-1tz.1](sase-1tz.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.7][1] | Need earlier phase notes and remaining work context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md

<!-- sase:referenced-by:end -->
