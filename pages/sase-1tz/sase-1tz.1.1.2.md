# Bead: sase-1tz.1.1.2 — Settle held workspaces once per evidence fingerprint with change-only +1s

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.2` · **Size:** medium
**Created:** 2026-11-19 07:28:41 EST · **Closed:** 2026-11-19 09:57:15 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

held_settle: persist an evidence fingerprint and a cheap stat signature with the retention record. Later stale-running cleanup passes over unchanged evidence then skip git probes, snapshots, decision-sheet publishing, and +1s. Add the hourly still-held heartbeat for undismissed rows.

## Notes

[2026-11-19T14:56:32Z · sase-1tz.1.1.2] Measurement before-numbers (read-only, athena, 2026-11-19 ~09:04 EST): notification-store generation 345269 -> 345289 in 60 s (~20 advances/min) on a 7.3 MB notifications.jsonl; audit baseline was ~16 full rewrites/min and 5,500+ "retained with other dirt" lines per workspace over Nov 17-19. After-install repeat command: g1=$(cat ~/.sase/notifications/notifications.jsonl.generation); sleep 60; g2=$(cat ~/.sase/notifications/notifications.jsonl.generation); echo $((g2-g1)) (expect ~0-1 per hour per hold instead of ~16-20/min).

[2026-11-19T14:56:52Z · sase-1tz.1.1.2] PROPOSED FOLLOW-UP: just check _setup gate (tools/validate_sase_core_rs) fails workspace-wide with "disk_inventory_wire_schema_version() returned stale schema: got 2, expected 1" because the linked sase-core checkout is at eabe416c (wire v2, sibling phase sase-1tz.1.1.4 unknown_sizes) while this checkout pins d8681dbb. Reproduces identically on the clean base tree (verified via git stash), so it is not caused by held_settle; the pin move belongs to sase-1tz.1.1.4. Verified instead via repo-wide mypy, ruff, symvision, toobig, keep-sorted, docs-lint, epic-symbol freshness, and the affected pytest files (all passing).

[2026-11-19T14:57:15Z · sase-1tz.1.1.2] held_settle done and verified: retention records now persist an evidence fingerprint + cheap stat signature (index/HEAD/branch-ref/root mtimes, no subprocess) + probed_at. Unchanged passes skip git probes, snapshots, decision-sheet publishing, pins, record writes, and +1s (hourly heartbeat aside); changed evidence re-settles with one +1 naming the change; dismissed rows latch with no resurrection after compaction. 7 new tests in tests/test_held_settle_evidence.py pass; updated the 3 existing tests that encoded always-resettle. Docs updated (docs/reference/agents/workspaces.md). Verified: repo-wide mypy/ruff/symvision/toobig/keep-sorted/docs-lint/epic-symbols clean; affected pytest files pass (held_settle, monitor retention, stale cleanup, hijack, chop triggers). just check _setup validator failure is pre-existing on the clean tree (sibling wire-v2 skew, recorded as PROPOSED FOLLOW-UP). No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1tz.1.1.1](sase-1tz.1.1.1.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.2/README.md) | [sase-1tz.1.1.2](sase-1tz.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c7b87c`](https://github.com/sase-org/sase/commit/5c7b87c71a9c6c41c22d7f3e85ea71fe0b7215e7) | feat(retention): settle held workspaces once per evidence fingerprint | [sase-1tz.1.1.2](sase-1tz.1.1.2.md) | 2026-11-19 09:59:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.2][1] | check notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.2/README.md

<!-- sase:referenced-by:end -->
