# Bead: sase-1tz — Fix the 13 ranked defects from the apollo/athena notification and log audit

[Bead Pages](../README.md) / sase-1tz

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.land`
**Created:** 2026-11-19 07:09:38 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/notification_log_audit_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md

<!-- sase:links:end -->

## Description

Disk pressure names the owners it could not measure, and recovery runs even when attribution is incomplete. Held workspaces stop rewriting the notification store. agent_publication and the error digest report each cause once, with true counts. Measured TUI stalls shrink. The six targeted defects (prompt_prose wire, update races, Telegram transport, Codex bundle cap, triage request-id retry, gateway WAL checkpoint) are fixed. Notifications, logs, and state files follow their stated dedup and retention rules on both hosts.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1tz.1](sase-1tz.1.md) | Honest disk attribution and the held-workspace re-settlement loop (items 1-2) | ✓ closed | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.2](sase-1tz.2.md) | Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5) | ◐ in_progress | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.3](sase-1tz.3.md) | Targeted high-confidence defect fixes (items 6-10) | ◐ in_progress | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.4](sase-1tz.4.md) | Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13) | ◐ in_progress | xlarge | 2026-11-19 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1tz: Fix the 13 ranked defects from the apollo/athena notification and log audit [in_progress]"]
    n1["sase-1tz.1: Honest disk attribution and the held-workspace re-settlement loop (items 1-2) [closed]"]
    n2["sase-1tz.1.1: Honest disk attribution and an end to the held-workspace re-settlement loop [closed]"]
    n3["sase-1tz.1.1.1: Coalesce identical +1s and stop rewriting the store for dismissed rows [closed]"]
    n4["sase-1tz.1.1.2: Settle held workspaces once per evidence fingerprint with change-only +1s [closed]"]
    n5["sase-1tz.1.1.3: Check that starter-inherited repo lists stay inside the monitor's workspace [closed]"]
    n6["sase-1tz.1.1.4: Represent unmeasured disk owners as unknown, never 0 B complete [closed]"]
    n7["sase-1tz.1.1.5: Measure workspace and owner roots first under their own budget [closed]"]
    n8["sase-1tz.1.1.6: Recover first, name unmeasured owners, and escalate missed recovery targets [closed]"]
    n9["sase-1tz.1.1.7: Report repeated managed-tmp reaper skips as one standing state [closed]"]
    n10["sase-1tz.2: Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5) [in_progress]"]
    n11["sase-1tz.2.1: Publication de-flap, truthful error digests, and TUI stall reduction [in_progress]"]
    n12["sase-1tz.2.1.1: Group the scheduler error ring by signature with durable interval counts [closed]"]
    n13["sase-1tz.2.1.10: Find and fix the top cyclic-garbage producers and heap retainers [in_progress]"]
    n14["sase-1tz.2.1.11: Move sampled synchronous filesystem work off the TUI main thread [closed]"]
    n15["sase-1tz.2.1.12: Cache compiled query profiles and cut per-second clan runtime work [closed]"]
    n16["sase-1tz.2.1.13: Measure the combined TUI result and settle the TUI task beads [in_progress]"]
    n17["sase-1tz.2.1.2: Render one digest line per cause with true totals, coverage, and pruning [closed]"]
    n18["sase-1tz.2.1.3: Turn repeated publication failures into standing alerts with backoff [closed]"]
    n19["sase-1tz.2.1.4: Give drain cleanup a budget it can finish and sweep stranded publisher scratch [closed]"]
    n20["sase-1tz.2.1.5: Bound inventory_build with reuse, an incremental history cache, and scoped queries [in_progress]"]
    n21["sase-1tz.2.1.6: Keep deferred prompt sources alive and add an audited terminal state [in_progress]"]
    n22["sase-1tz.2.1.7: Make the publication doctor checks report standing and terminal state [in_progress]"]
    n23["sase-1tz.2.1.8: Rotate tui_stalls.jsonl, tolerate torn lines, and write fault headers only on faults [closed]"]
    n24["sase-1tz.2.1.9: Stop policy-initiated garbage collections from blocking the loop for seconds [closed]"]
    n25["sase-1tz.3: Targeted high-confidence defect fixes (items 6-10) [in_progress]"]
    n26["sase-1tz.4: Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13) [in_progress]"]
    n0 --> n1
    n1 --> n2
    n2 --> n3
    n2 --> n4
    n2 --> n5
    n2 --> n6
    n2 --> n7
    n2 --> n8
    n2 --> n9
    n0 --> n10
    n10 --> n11
    n11 --> n12
    n11 --> n13
    n11 --> n14
    n11 --> n15
    n11 --> n16
    n11 --> n17
    n11 --> n18
    n11 --> n19
    n11 --> n20
    n11 --> n21
    n11 --> n22
    n11 --> n23
    n11 --> n24
    n0 --> n25
    n0 --> n26
    n1 -.-> n10
    n3 -.-> n4
    n3 -.-> n8
    n6 -.-> n7
    n6 -.-> n8
    n10 -.-> n25
    n12 -.-> n17
    n12 -.-> n18
    n13 -.-> n16
    n14 -.-> n16
    n15 -.-> n16
    n18 -.-> n20
    n18 -.-> n22
    n19 -.-> n20
    n19 -.-> n21
    n21 -.-> n22
    n23 -.-> n16
    n23 -.-> n24
    n24 -.-> n13
    n24 -.-> n16
    n25 -.-> n26
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) | [sase-1tz.1](sase-1tz.1.md) | 0 |
| [bbugyi200.athena.sase-1tz.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.1/README.md) | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2 |
| [bbugyi200.athena.sase-1tz.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.2/README.md) | [sase-1tz.1.1.2](sase-1tz.1.1.2.md) | 1 |
| [bbugyi200.athena.sase-1tz.1.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.1.3.md) | [sase-1tz.1.1.3](sase-1tz.1.1.3.md) | 1 |
| [bbugyi200.athena.sase-1tz.1.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md) | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2 |
| [bbugyi200.athena.sase-1tz.1.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.5/README.md) | [sase-1tz.1.1.5](sase-1tz.1.1.5.md) | 1 |
| [bbugyi200.athena.sase-1tz.1.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md) | [sase-1tz.1.1.6](sase-1tz.1.1.6.md) | 1 |
| [bbugyi200.athena.sase-1tz.1.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md) | [sase-1tz.1.1.7](sase-1tz.1.1.7.md) | 1 |
| [bbugyi200.athena.sase-1tz.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.land/README.md) | [sase-1tz.1.1](sase-1tz.1.1.md) | 1 |
| [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) | [sase-1tz.2](sase-1tz.2.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md) | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.10/README.md) | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md) | [sase-1tz.2.1.11](sase-1tz.2.1.11.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.12/README.md) | [sase-1tz.2.1.12](sase-1tz.2.1.12.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.13/README.md) | [sase-1tz.2.1.13](sase-1tz.2.1.13.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md) | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md) | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md) | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.5/README.md) | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.6/README.md) | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.7/README.md) | [sase-1tz.2.1.7](sase-1tz.2.1.7.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.8/README.md) | [sase-1tz.2.1.8](sase-1tz.2.1.8.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md) | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.land/README.md) | [sase-1tz.2.1](sase-1tz.2.1.md) | 0 |
| [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3/README.md) | [sase-1tz.3](sase-1tz.3.md) | 0 |
| [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4/README.md) | [sase-1tz.4](sase-1tz.4.md) | 0 |
| [bbugyi200.athena.sase-1tz.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.land/README.md) | [sase-1tz](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63fc5cc`](https://github.com/sase-org/sase/commit/63fc5ccc4c6fed1adcb09eadc508587338dd508e) | test(monitor): live foreign starter repos do not retain | [sase-1tz.1.1.3](sase-1tz.1.1.3.md) | 2026-11-19 08:02:36 EST |
| sase | [`06ae058`](https://github.com/sase-org/sase/commit/06ae058b5fff147bfb39ec81f58a6788141071a5) | feat(axe): report managed tmp skips as standing state | [sase-1tz.1.1.7](sase-1tz.1.1.7.md) | 2026-11-19 08:33:03 EST |
| sase-core | [`sase-core@d8681db`](https://github.com/sase-org/sase-core/commit/d8681dbbff2b435cbb83d7052db7c118afcd9b67) | feat(notifications): coalesce plus-one updates | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2026-11-19 08:54:40 EST |
| sase | [`ed5cb12`](https://github.com/sase-org/sase/commit/ed5cb12ef9ccd656302dbacf045a856e9e77f6c2) | feat(notifications): coalesce repeated plus-ones | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2026-11-19 08:55:52 EST |
| sase-core | [`sase-core@eabe416`](https://github.com/sase-org/sase-core/commit/eabe416cb5691876e3fd275e40769fcfbd18788d) | feat!: bump disk-inventory wire to v2 with per-row size state | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2026-11-19 09:10:50 EST |
| sase | [`6ee5f85`](https://github.com/sase-org/sase/commit/6ee5f8560caa8ec689349a3b5767954e5d99e4d6) | feat(disk): render unmeasured owners instead of 0 B complete | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2026-11-19 09:12:00 EST |
| sase | [`5c7b87c`](https://github.com/sase-org/sase/commit/5c7b87c71a9c6c41c22d7f3e85ea71fe0b7215e7) | feat(retention): settle held workspaces once per evidence fingerprint | [sase-1tz.1.1.2](sase-1tz.1.1.2.md) | 2026-11-19 09:59:07 EST |
| sase | [`7b6a44a`](https://github.com/sase-org/sase/commit/7b6a44a100e5090d8cc98481377d01af40c54aca) | feat(disk): recover under pressure before attributing owners | [sase-1tz.1.1.6](sase-1tz.1.1.6.md) | 2026-11-19 10:26:11 EST |
| sase | [`6f21d01`](https://github.com/sase-org/sase/commit/6f21d01de33c0fa13f3479eaeb0091f7607dbd73) | feat(disk): prioritize workspace root measurements | [sase-1tz.1.1.5](sase-1tz.1.1.5.md) | 2026-11-19 10:34:30 EST |
| sase--plans | [`sase--plans@2b4d1de`](https://github.com/sase-org/sase--plans/commit/2b4d1de2ac50f24091306eb54af02b1e20e70126) | chore(plans): mark outage disk attribution epic done | [sase-1tz.1.1](sase-1tz.1.1.md) | 2026-11-19 10:50:35 EST |
| sase | [`ffb7d33`](https://github.com/sase-org/sase/commit/ffb7d33edb8ae72b9bc2f2ee2af9d2f426174fe6) | perf(ace): memoize built-in query profiles and clan runtime wire payloads | [sase-1tz.2.1.12](sase-1tz.2.1.12.md) | 2026-11-19 12:47:49 EST |
| sase-core | [`sase-core@3a32a23`](https://github.com/sase-org/sase-core/commit/3a32a233f0fb6fb8c894008eb52b407b2e50b4a9) | feat(axe-error): add volatile-token normalizer and signature grouping | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2026-11-19 12:48:47 EST |
| sase-core | [`sase-core@5ad6013`](https://github.com/sase-org/sase-core/commit/5ad60139499e9149dbc6a1a3db01ec7f088134b0) | feat(publication): raise cleanup timeout to 15s | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2026-11-19 12:50:13 EST |
| sase | [`1ae81b4`](https://github.com/sase-org/sase/commit/1ae81b40987b9bd19fefc8abc926eb703e17108d) | feat(axe): add durable error counts with signature grouping | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2026-11-19 12:50:24 EST |
| sase | [`c756511`](https://github.com/sase-org/sase/commit/c756511c1113809840c79d5dda5d25d41b5c164a) | feat(agents-sync): reserve 15s for publisher drain cleanup | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2026-11-19 12:51:37 EST |
| sase | [`238ef42`](https://github.com/sase-org/sase/commit/238ef42df90900ae0cb78c900de9b55a23439de2) | perf(ace): move sampled main-thread filesystem work off the TUI loop | [sase-1tz.2.1.11](sase-1tz.2.1.11.md) | 2026-11-19 14:55:11 EST |
| sase | [`96b3716`](https://github.com/sase-org/sase/commit/96b3716cb32b0888fcdba7ab8861cd781087d973) | feat(axe): render grouped scheduler error digests with true totals | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 2026-11-19 14:57:27 EST |
| sase | [`afb0705`](https://github.com/sase-org/sase/commit/afb070580a159fc383b8b5f52e29ea649328c096) | feat(tui): rotate tui\_stalls.jsonl, tolerate torn lines, and spool fault logs | [sase-1tz.2.1.8](sase-1tz.2.1.8.md) | 2026-11-19 14:58:03 EST |
| sase-core | [`sase-core@3c3263f`](https://github.com/sase-org/sase-core/commit/3c3263fb98cfe2185764f8e6ea6e3b0aaae0a40c) | feat(publication): add standing-alert decider with capped backoff | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2026-11-19 15:22:42 EST |
| sase | [`5f719a5`](https://github.com/sase-org/sase/commit/5f719a5361c407086763f5f2dd71282755cc1713) | feat(agents-sync): report repeated publication failures as standing alerts with backoff | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2026-11-19 16:39:00 EST |
| sase | [`49b96a9`](https://github.com/sase-org/sase/commit/49b96a9c5095bf677829c980bcfe8b658d0b5182) | feat(tui): gate policy GC pauses | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 2026-11-19 17:03:45 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.1][1] | Need the governing epic DECISIONS before implementing its notification-store phase | 1 |
| read-by | [agent:sase-1tz.1.1.4][2] | Need top-level parent epic DECISIONS which are final | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md

<!-- sase:referenced-by:end -->
