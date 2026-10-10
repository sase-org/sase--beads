# Bead: sase-1j6.10.6 — Live episode report on settlement, honest titles, and per-death escalation keys

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.6` · **Size:** medium
**Created:** 2026-10-10 08:09:09 EDT · **Closed:** 2026-10-10 11:07:18 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

episode-polish: refresh the live report and the row's inline snapshot on every job settlement (consuming refresh_episode_report and dropping its epic-symbol row), map every terminal outcome in the Now column, fix episode titles and the unknown-episode fallback, key escalations per death, carry every relaunched agent's evidence files, and apply the quiet_declines decision.

## Notes

[2026-10-10T15:07:06Z · sase-1j6.10.6] PROPOSED FOLLOW-UP: just check symvision fails on clean base for ArtifactIndexProjection in src/sase/agents/catalog/_sources.py (unused public class); identical with and without episode-polish changes, needs its own owner

[2026-10-10T15:07:18Z · sase-1j6.10.6] episode-polish done: settlement refreshes live report + row snapshot via reconcile with cursors unchanged; Now maps all terminal outcomes (stopped/noop/epic_launch_failed/etc, never RUNNING when finished); titles show short sha with a sase update fallback (no sase@, no unknown); escalations/resurfaces keyed per death by artifacts timestamp; episode row carries every agent error_report.md + evidence bundle; quiet_declines=quiet honored. Verified: 46 focused auto-restart tests + full 123-test auto-restart suite green; sase tool run check lint stages (ruff/mypy/symvision) show only the pre-existing base-identical ArtifactIndexProjection symvision failure (recorded as PROPOSED FOLLOW-UP); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1j6.10.5](sase-1j6.10.5.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1j6.10.7](sase-1j6.10.7.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.6/README.md) | [sase-1j6.10.6](sase-1j6.10.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df47dd8`](https://github.com/sase-org/sase/commit/df47dd875b0870815de1adffb4b82163cf260cc3) | feat(auto-restart): polish episode report settlement, titles and dedup | [sase-1j6.10.6](sase-1j6.10.6.md) | 2026-10-10 11:09:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.6][1] | Need phase scope and design | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.6/README.md

<!-- sase:referenced-by:end -->
