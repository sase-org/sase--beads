# Bead: sase-1tz.1.1.5 — Measure workspace and owner roots first under their own budget

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.5` · **Size:** medium
**Created:** 2026-11-19 07:28:41 EST · **Closed:** 2026-11-19 10:32:45 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

owner_first: workspace checkouts and owner roots are sized before managed-tmp buckets and the stray walk, under a budget separate from the shared stray budget. Record the sase-1bf.4 regression finding and the du tolerance measured on apollo and athena.

## Notes

[2026-11-19T14:48:57Z · sase-1tz.1.1.5] owner_first is implemented: workspace checkout, shared primary, fixed SASE state, artifact-run, and managed-tmp roots receive one du -skx pass before bucket/detail/stray scans. The independent owner pass uses up to four concurrent du processes, a 60s per-root timeout, and a 90s overall deadline; the existing 5s/50k shared budget remains for details and strays.

Read-only pre-install baseline on 2026-11-19 used `sase workspace list --all --json`, `sase disk list --json`, and `du -skx -- PATH`. Existing disk-list workspace rows were unmeasured:0 except Apollo bob-cli workspace, which was lower_bound:0. Direct du output in KiB, workspace root / shared primary:
Apollo: bob-cli 38824416 / 9841888 (workspace 9.4s); body 5048 / 8644; cash 35160 / 15004; dev 5072 / 13128; job 294312 / 71408; love 147532 / 39044; nut missing / 208; sase 19820544 / 6425420 (workspace 9.9s); tailnet 1110820 / 77392.
Athena: actstat 1616524 / 2088416; body 3763860 / 9576; cash 9884 / 13536; dev 3792532 / 14940; job 64796 / 61788; love 151908 / 41392; bob-cli 36779432 / 7660584 (workspace 19.4s); sase 88334964 / 10143024 (workspace 42.8s); sase-spotify 14720 / 16428; tailnet 988256 / 76864.

The code uses the same du -skx measurement and stores its KiB result multiplied by 1024, so 0 KiB difference is expected for an unchanged root. Compare each workspace row to du on its own path; do not sum nested detail rows, since the classifier removes overlap, including shared Git object paths. After install, repeat `sase disk list --json` on each host and run `du -skx -- PATH` for every section=workspaces path. Post-install comparison remains pending the human-owned global install.

[2026-11-19T15:32:45Z · sase-1tz.1.1.5] Implemented first-pass measurement for workspace, SASE state, artifacts, and managed-temp owner roots with a 90s aggregate / 60s-per-root / 4-way budget ahead of the shared detail budget. just check passed (scoped pytest 21m26s). On Athena all 10 workspace owner roots were measured and matched fresh du -skx totals exactly (0 KiB delta). Recorded sase-1bf.4 findings and budgets in bead notes; Apollo post-install comparison remains to repeat after the human-owned global install. epic-symbol check found no leftovers.

## Dependencies

- **Depends on:** [sase-1tz.1.1.4](sase-1tz.1.1.4.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.5/README.md) | [sase-1tz.1.1.5](sase-1tz.1.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f21d01`](https://github.com/sase-org/sase/commit/6f21d01de33c0fa13f3479eaeb0091f7607dbd73) | feat(disk): prioritize workspace root measurements | [sase-1tz.1.1.5](sase-1tz.1.1.5.md) | 2026-11-19 10:34:30 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.5][1] | Need the phase scope, design file, and prior work notes before implementing the assigned phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.5/README.md

<!-- sase:referenced-by:end -->
