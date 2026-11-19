# Bead: sase-1tz.1.1 — Honest disk attribution and an end to the held-workspace re-settlement loop

[Bead Pages](../README.md) / [sase-1tz.1](sase-1tz.1.md) / sase-1tz.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.land`
**Created:** 2026-11-19 07:28:40 EST · **Closed:** 2026-11-19 10:48:20 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/outage_disk_attribution_and_held_workspaces.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md

<!-- sase:links:end -->

## Description

Disk inventory reports unmeasured owners as unknown rather than 0 B, and measures workspace roots before anything else. Pressure recovery runs whether or not attribution is complete, and a missed target produces a distinct escalation. Held workspaces settle once per evidence fingerprint. Their notices get a +1 only when evidence changes, plus an hourly heartbeat on undismissed rows. The notification store skips the rewrite for coalesced and dismissed-row +1s.

## Notes

[2026-11-19T15:47:57Z · sase-1tz.1.1.land] Land follow-up triage: (1) sase-1tz.1.1.1 PROPOSED FOLLOW-UP (test_prompt_bar_hot_spare.py full-lane KeyError text-area--gutter) is a semantic duplicate of flake task sase-1q8, corroborated with +1 (now +2 reports); no new task. (2) sase-1tz.1.1.2 PROPOSED FOLLOW-UP (just check _setup validator: disk_inventory_wire_schema_version stale, got 2 expected 1) declined: it was transient sibling skew that this epic's own unknown_sizes commit 6ee5f8560c resolved by moving sase-core-revision.txt to eabe416c and updating tools/validate_sase_core_rs; tools/validate_sase_core_rs exits 0 and sase tool run check 59dbd43b passed on the combined tree.

[2026-11-19T15:48:20Z · sase-1tz.1.1.land] Verified all 7 phases closed with notes addressed and parent DECISIONS honored (held_heartbeat=yes: hourly still-held +1 on undismissed rows only, dismissed latch beside retention record). Read source and commits 63fc5ccc4c (starter_scope regression test; sase-1rg.3 already scopes foreign starter repos), 06ae058b5f (standing managed-tmp skips incl. environ-unreadable class), ed5cb12ef9 + sase-core d8681dbb (store_guard: skipped_dismissed/coalesced no-ops under the exclusive lock with no rewrite or generation bump; cli +1 opts in; prune publisher handles new actions), 6ee5f8560c + sase-core eabe416c (unknown_sizes: measured/lower_bound/unmeasured, wire v2, honest disk list/doctor/residual), 5c7b87c71a (held_settle: evidence fingerprint + stat signature + probed_at, 30m re-probe, change-only +1s, one-line-per-change logs), 7b6a44a100 (pressure_recovery: reap first, 20s fail-open inventory, episode-scoped notice and escalation keys, check_error on missed target), 6f21d01de3 (owner_first: 90s/60s-per-root/4-way du pass before detail and stray scans; misleading test replaced by real-sizer test). sase-core-revision.txt pin eabe416c includes both sase-core commits. Coordination notes present on sase-zw.8, sase-1bf.4, sase-1rg.3, sase-11h; measurement summaries for all 4 measuring phases on sase-1tz.1. Integration: only non-epic commits since start (6e1fc2536f monitor staged joins, c4cb77b3b8 bead SQLite tests) do not touch disk/notification/retention; all disk-footprint consumers are in epic-touched files, so no integration edits were needed. Verification: 505 epic-focused tests passed; tools/validate_sase_core_rs exit 0; sase tool run check 59dbd43b passed. Follow-ups: prompt-bar flake +1'd onto sase-1q8; _setup wire-skew proposal declined as resolved in-epic by 6ee5f8560c. No epic-symbol entries. Post-install live acceptance (athena generation rate, apollo disk_pressure rows and du comparison) stays pending the human-owned global install.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.land/README.md) | [sase-1tz.1.1](sase-1tz.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@2b4d1de`](https://github.com/sase-org/sase--plans/commit/2b4d1de2ac50f24091306eb54af02b1e20e70126) | chore(plans): mark outage disk attribution epic done | [sase-1tz.1.1](sase-1tz.1.1.md) | 2026-11-19 10:50:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.1][1] | Need the parent epic decisions and complete design context for this phase | 1 |
| read-by | [agent:sase-1tz.1.1.2][2] | need epic scope and decisions | 1 |
| read-by | [agent:sase-1tz.1.1.4][3] | Need parent epic DECISIONS which are final for this phase | 1 |
| read-by | [agent:sase-1tz.1.1.6][4] | Need parent epic DECISIONS that this phase must honor | 2 |
| read-by | [agent:sase-1tz.1.1.7][5] | Need epic decisions and design constraints for phase implementation | 1 |
| read-by | [agent:sase-1tz.1.1.land][6] | Need the epic scope, children, and linked plan file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.land/README.md

<!-- sase:referenced-by:end -->
