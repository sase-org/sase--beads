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

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md

<!-- sase:links:end -->

## Description

Disk pressure names the owners it could not measure, and recovery runs even when attribution is incomplete. Held workspaces stop rewriting the notification store. agent_publication and the error digest report each cause once, with true counts. Measured TUI stalls shrink. The six targeted defects (prompt_prose wire, update races, Telegram transport, Codex bundle cap, triage request-id retry, gateway WAL checkpoint) are fixed. Notifications, logs, and state files follow their stated dedup and retention rules on both hosts.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1tz.1](sase-1tz.1.md) | Honest disk attribution and the held-workspace re-settlement loop (items 1-2) | ✓ closed | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.2](sase-1tz.2.md) | Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5) | ✓ closed | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.3](sase-1tz.3.md) | Targeted high-confidence defect fixes (items 6-10) | ✓ closed | xlarge | 2026-11-19 | 1 | 0 |
| [sase-1tz.4](sase-1tz.4.md) | Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13) | ◐ in_progress | xlarge | 2026-11-19 | 1 | 0 |

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
| [bbugyi200.athena.sase-1tz.2.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.10/README.md) | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md) | [sase-1tz.2.1.11](sase-1tz.2.1.11.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.12/README.md) | [sase-1tz.2.1.12](sase-1tz.2.1.12.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.13.md) | [sase-1tz.2.1.13](sase-1tz.2.1.13.md) | 0 |
| [bbugyi200.athena.sase-1tz.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md) | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md) | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md) | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md) | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.6/README.md) | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2 |
| [bbugyi200.athena.sase-1tz.2.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.7/README.md) | [sase-1tz.2.1.7](sase-1tz.2.1.7.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.8/README.md) | [sase-1tz.2.1.8](sase-1tz.2.1.8.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md) | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 1 |
| [bbugyi200.athena.sase-1tz.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.land.md) | [sase-1tz.2.1](sase-1tz.2.1.md) | 4 |
| [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) | [sase-1tz.3](sase-1tz.3.md) | 0 |
| [bbugyi200.athena.sase-1tz.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md) | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2 |
| [bbugyi200.athena.sase-1tz.3.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.10/README.md) | [sase-1tz.3.1.10](sase-1tz.3.1.10.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.11/README.md) | [sase-1tz.3.1.11](sase-1tz.3.1.11.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md) | [sase-1tz.3.1.2](sase-1tz.3.1.2.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md) | [sase-1tz.3.1.3](sase-1tz.3.1.3.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.4/README.md) | [sase-1tz.3.1.4](sase-1tz.3.1.4.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.1.5.md) | [sase-1tz.3.1.5](sase-1tz.3.1.5.md) | 1 |
| [bbugyi200.athena.sase-1tz.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.6/README.md) | [sase-1tz.3.1.6](sase-1tz.3.1.6.md) | 0 |
| [bbugyi200.athena.sase-1tz.3.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md) | [sase-1tz.3.1.7](sase-1tz.3.1.7.md) | 0 |
| [bbugyi200.athena.sase-1tz.3.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.8/README.md) | [sase-1tz.3.1.8](sase-1tz.3.1.8.md) | 0 |
| [bbugyi200.athena.sase-1tz.3.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md) | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 2 |
| [bbugyi200.athena.sase-1tz.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md) | [sase-1tz.3.1](sase-1tz.3.1.md) | 1 |
| [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) | [sase-1tz.4](sase-1tz.4.md) | 0 |
| [bbugyi200.athena.sase-1tz.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.1/README.md) | [sase-1tz.4.1.1](sase-1tz.4.1.1.md) | 1 |
| [bbugyi200.athena.sase-1tz.4.1.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.10.md) | [sase-1tz.4.1.10](sase-1tz.4.1.10.md) | 0 |
| [bbugyi200.athena.sase-1tz.4.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.11/README.md) | [sase-1tz.4.1.11](sase-1tz.4.1.11.md) | 1 |
| [bbugyi200.athena.sase-1tz.4.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.12/README.md) | [sase-1tz.4.1.12](sase-1tz.4.1.12.md) | 1 |
| [bbugyi200.athena.sase-1tz.4.1.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.13.md) | [sase-1tz.4.1.13](sase-1tz.4.1.13.md) | 0 |
| [bbugyi200.athena.sase-1tz.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.2/README.md) | [sase-1tz.4.1.2](sase-1tz.4.1.2.md) | 2 |
| [bbugyi200.athena.sase-1tz.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.3/README.md) | [sase-1tz.4.1.3](sase-1tz.4.1.3.md) | 2 |
| [bbugyi200.athena.sase-1tz.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.4/README.md) | [sase-1tz.4.1.4](sase-1tz.4.1.4.md) | 0 |
| [bbugyi200.athena.sase-1tz.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md) | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 0 |
| [bbugyi200.athena.sase-1tz.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.6/README.md) | [sase-1tz.4.1.6](sase-1tz.4.1.6.md) | 1 |
| [bbugyi200.athena.sase-1tz.4.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.7/README.md) | [sase-1tz.4.1.7](sase-1tz.4.1.7.md) | 1 |
| [bbugyi200.athena.sase-1tz.4.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.8/README.md) | [sase-1tz.4.1.8](sase-1tz.4.1.8.md) | 1 |

… and 3 more agents

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
| sase | [`225bfb7`](https://github.com/sase-org/sase/commit/225bfb7ff24084ad4ffe3e9ba962d6d8c478784a) | perf(tui): replace skill-use whole-file snapshot cache with targeted scans | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 2026-11-19 17:34:31 EST |
| sase-core | [`sase-core@6eedf0a`](https://github.com/sase-org/sase-core/commit/6eedf0a6544cfd9da279a29cd42c245d70404a04) | feat(agent-publication-recovery): add terminal unrecoverable deferred-prompt outcome | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2026-11-19 17:49:43 EST |
| sase | [`3d3d0f5`](https://github.com/sase-org/sase/commit/3d3d0f583d0790aa9ebab3af08d4fe2f32cb9904) | feat(agents-sync): retire terminal deferred prompts as unrecoverable | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2026-11-19 17:51:28 EST |
| sase | [`77c0f23`](https://github.com/sase-org/sase/commit/77c0f23375e70c2b684050a3267366f1e6dbdd40) | feat(doctor): group publication outbox by cause, settle terminal rows, calm stale-only protection | [sase-1tz.2.1.7](sase-1tz.2.1.7.md) | 2026-11-19 18:45:53 EST |
| sase-core | [`sase-core@80fcc86`](https://github.com/sase-org/sase-core/commit/80fcc862ba4b10c936eb6b484470632729eefbc3) | feat(agent-archive): filter dismissed bundles by identity prefix | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2026-11-19 20:12:40 EST |
| sase | [`fb85972`](https://github.com/sase-org/sase/commit/fb85972f27438a2ceee0304862aaa3446106fb80) | perf(agents-sync): reuse scoped hood inventory | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 2026-11-19 21:01:04 EST |
| sase | [`8cf9d8e`](https://github.com/sase-org/sase/commit/8cf9d8e5465994f9c1a34a5075a4bb7ea0ed9d47) | fix(doctor): keep cause detail in grouped publication issues and review scratch sweep | [sase-1tz.2.1](sase-1tz.2.1.md) | 2026-11-20 08:03:07 EST |
| sase-core | [`sase-core@5c8ccd6`](https://github.com/sase-org/sase-core/commit/5c8ccd6b879db3edb7444dec1dd71bc99f8c4eca) | fix(agent-publication): ignore volatile detail in standing alert decisions | [sase-1tz.2.1](sase-1tz.2.1.md) | 2026-11-20 09:04:49 EST |
| sase | [`d18b499`](https://github.com/sase-org/sase/commit/d18b499d4d5582e2390da8e9af1f6fb31208f582) | feat(agents-sync): finish publication de-flap, error accounting, and GC pressure gate | [sase-1tz.2.1](sase-1tz.2.1.md) | 2026-11-20 09:06:32 EST |
| sase--plans | [`sase--plans@43f86af`](https://github.com/sase-org/sase--plans/commit/43f86aff6cd7415391db661d71b45ff79cc1144e) | chore(plans): mark noise\_publication\_digests\_tui\_stalls done | [sase-1tz.2.1](sase-1tz.2.1.md) | 2026-11-20 09:08:14 EST |
| sase | [`9bbdeec`](https://github.com/sase-org/sase/commit/9bbdeec5f45d1a8a407d03839a912c413e71de18) | test(dev\_update): add update-overlap reproducer for jobs, launches, and native code | [sase-1tz.3.1.2](sase-1tz.3.1.2.md) | 2026-11-20 10:50:59 EST |
| sase | [`b6f6c63`](https://github.com/sase-org/sase/commit/b6f6c63e3e4bdbbdd188b68d341b46f2dbbe3fcb) | fix(triage): recover from gate request id conflicts | [sase-1tz.3.1.11](sase-1tz.3.1.11.md) | 2026-11-20 10:56:33 EST |
| sase | [`f9b8800`](https://github.com/sase-org/sase/commit/f9b88003413260bc1c85ecb39ea1d794a6d17db5) | fix(dev-update): treat a prebuilt Rust cache miss as a miss | [sase-1tz.3.1.5](sase-1tz.3.1.5.md) | 2026-11-20 11:00:46 EST |
| sase-core | [`sase-core@142ed42`](https://github.com/sase-org/sase-core/commit/142ed4212dcb61b2b08a1f487d057681fae32c43) | feat(instruction\_manifest): record compile-time bundle compaction | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 2026-11-20 11:22:05 EST |
| sase | [`41f95c8`](https://github.com/sase-org/sase/commit/41f95c82cfdf0c24456035cf5e968184a696b374) | feat(instructions): compact oversize provider root bundles to fit max\_bytes | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 2026-11-20 11:24:00 EST |
| sase | [`3ae6b09`](https://github.com/sase-org/sase/commit/3ae6b09b72d8efed932981077cbb2266daa631fd) | feat(axe): defer and retry scheduler jobs that overlap a code swap | [sase-1tz.3.1.3](sase-1tz.3.1.3.md) | 2026-11-20 11:30:49 EST |
| sase-core | [`sase-core@0939137`](https://github.com/sase-org/sase-core/commit/0939137425c091bbbbbdc37b524e971268c16614) | feat(artifact-link): add prompt\_prose origin to ArtifactLinkOriginWire | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2026-11-20 11:53:27 EST |
| sase | [`eca97ab`](https://github.com/sase-org/sase/commit/eca97ab5a75ec31ff224af02472c03198a21f9e3) | feat(artifact-links): add host-origin constant and prompt\_prose binding contract test | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2026-11-20 11:55:13 EST |
| sase | [`7c73ee3`](https://github.com/sase-org/sase/commit/7c73ee386637bf08c01b0450d76284da19f50a4e) | feat(launch): defer and retry launches and finalizers that overlap a code swap | [sase-1tz.3.1.4](sase-1tz.3.1.4.md) | 2026-11-20 13:01:54 EST |
| sase | [`f6b4344`](https://github.com/sase-org/sase/commit/f6b4344d878ca883edf496d87b115f606dd91d6e) | feat(doctor): gate provider root bundle sizes in sase doctor and just check | [sase-1tz.3.1.10](sase-1tz.3.1.10.md) | 2026-11-20 13:20:04 EST |
| sase--plans | [`sase--plans@0210bca`](https://github.com/sase-org/sase--plans/commit/0210bca3373e82a82087becae6a6af4d3cb1a1bf) | chore(plans): mark defects\_wire\_swap\_telegram\_bundles\_triage done after landing sase-1tz.3.1 | [sase-1tz.3.1](sase-1tz.3.1.md) | 2026-11-20 13:39:46 EST |
| sase-core | [`sase-core@553387d`](https://github.com/sase-org/sase-core/commit/553387d39df464c4989e0deba2725f71cf32c60e) | fix(agent-index): treat busy -1 WAL checkpoint as busy and checkpoint passively in the gateway | [sase-1tz.4.1.1](sase-1tz.4.1.1.md) | 2026-11-20 14:24:35 EST |
| sase | [`2b18880`](https://github.com/sase-org/sase/commit/2b18880ef1c0d12bd75e37b90542f5447a73867b) | feat(triage): keep one task-triage notification row per bead across re-presentations | [sase-1tz.4.1.8](sase-1tz.4.1.8.md) | 2026-11-20 15:25:48 EST |
| sase-core | [`sase-core@2c33360`](https://github.com/sase-org/sase-core/commit/2c33360ad602932ccd63e6941b4751b979efe133) | feat(notifications): resurface reconciled rows when a named revision key changes | [sase-1tz.4.1.3](sase-1tz.4.1.3.md) | 2026-11-20 15:28:38 EST |
| sase | [`0386c59`](https://github.com/sase-org/sase/commit/0386c59150a9c3fa7e33a75a991e136d07672688) | feat(notifications): key remote-attention rows by stable request identity | [sase-1tz.4.1.3](sase-1tz.4.1.3.md) | 2026-11-20 15:31:49 EST |
| sase | [`bca49ea`](https://github.com/sase-org/sase/commit/bca49eadd11e70043e0fab05e140ee52a69fe35d) | feat(wait\_checks): raise one notice per failed root blocker and freeze its +1s | [sase-1tz.4.1.6](sase-1tz.4.1.6.md) | 2026-11-20 15:40:31 EST |
| sase | [`18e4f35`](https://github.com/sase-org/sase/commit/18e4f35a54d84c71e79d41d2bd74cabc8771429c) | feat(retention): schedule tool-run log horizon and age-rotate tui.log | [sase-1tz.4.1.12](sase-1tz.4.1.12.md) | 2026-11-20 15:50:07 EST |
| sase | [`f960f75`](https://github.com/sase-org/sase/commit/f960f758ca9bc3b88f0a722d5c9c8df14ed1b40f) | feat(agents-sync): memoize unchanged refresh verdicts | [sase-1tz.4.1.11](sase-1tz.4.1.11.md) | 2026-11-20 16:19:07 EST |
| sase | [`1115db9`](https://github.com/sase-org/sase/commit/1115db9e66d4ebc82114d74a7fc524eab0900b42) | feat(bead-triage): reconcile notification gates with sticky dismissal and settled-bundle reaping | [sase-1tz.4.1.9](sase-1tz.4.1.9.md) | 2026-11-20 16:40:14 EST |

… and 3 more commits

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.1][1] | Need the governing epic DECISIONS before implementing its notification-store phase | 1 |
| read-by | [agent:sase-1tz.1.1.4][2] | Need top-level parent epic DECISIONS which are final | 1 |
| read-by | [agent:sase-1tz.2.1.5--2][3] | Check the active parent epic context for the publication-performance lint finding | 1 |
| read-by | [agent:sase-1tz.3.1.land][4] | Confirm the containing epic stays open for its land agent | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->
