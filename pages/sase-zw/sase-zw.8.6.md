# Bead: sase-zw.8.6 — Complete host reclamation and combined verification evidence

[Bead Pages](../README.md) / [sase-zw.8](sase-zw.8.md) / sase-zw.8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.6` · **Size:** medium
**Created:** 2026-09-13 18:40:44 EDT · **Closed:** 2026-09-14 16:08:02 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

acceptance: verify the installed cohort, account for the prior cleanup decision, measure remaining owned reclamation and safe workspace compaction, and publish full acceptance evidence.

## Notes

[2026-09-14T20:05:23Z · sase-zw.8.6] PROPOSED FOLLOW-UP: Monitored just check-full rerun after global leak detector Git-env ignore fix - pre-fix just check-full completed 41665 passed/15 skipped but failed on 8 deterministic Git identity env false positives; post-fix focused reproducer and just check passed.

[2026-09-14T20:07:08Z · sase-zw.8.6] Evidence artifact: file:explicit:a0a0691996ca110fe07614a4 (sase-zw.8.6 acceptance evidence).

[2026-09-14T20:08:02Z · sase-zw.8.6] Verified core/LSP 0.34.28 installed cohort, core LD_LIBRARY_PATH just check, post-fix just check, and leak-detector repros; pre-fix check-full completed 41665 passed/15 skipped then failed on fixed Git-env detector false positive. Compacted safe workspaces, pruned authorized artifacts, resource doctor OK, no unowned >1GiB. Evidence file:explicit:a0a0691996ca110fe07614a4.

## Dependencies

- **Depends on:** [sase-zw.8.5](sase-zw.8.5.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.6/README.md) | [sase-zw.8.6](sase-zw.8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6b4bee9`](https://github.com/sase-org/sase/commit/6b4bee96ddfd93478264de0356ddbdf266d3cab7) | test(global-state): ignore harness git env in leak snapshots | [sase-zw.8.6](sase-zw.8.6.md) | 2026-09-14 16:10:06 EDT |
