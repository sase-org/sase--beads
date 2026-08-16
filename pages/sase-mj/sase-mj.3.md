# Bead: sase-mj.3 — Perf view registration and interaction

[Bead Pages](../README.md) / [sase-mj](README.md) / sase-mj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.032](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.032.md) · **Assignee:** `sase-mj.3` · **Size:** medium
**Created:** 2026-08-15 20:26:11 EDT · **Closed:** 2026-08-15 22:13:38 EDT
**Plan:** [202608/statistics\_perf\_view.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_perf_view.md)

## Description

perf_view: register Perf as the eighth Statistics view — tab strip, numbered selection, description, legends, grouping modes, non-project scope, lazy loading, and the contextual help methodology section.

## Notes

[2026-08-16T02:13:05Z · sase-mj.3] PROPOSED FOLLOW-UP: Pre-existing Symvision private-import failures on HEAD — just check / just _lint-symvision fail on models_panel_provider_* symbols and several _now helpers (vcs_log/fetch_cache, bead/project, prompt/search/dates); reproduced with this phase stashed, so it is not caused by Perf view registration.

[2026-08-16T02:13:38Z · sase-mj.3] Registered Perf as the eighth Statistics view: VIEW_ORDER/labels/descriptions (Perf/Prf), grouping (subsystem/provider/workflow with reload), lazy load + stale-group worker guard, dimmed project chip with '· not applied', empty-view bypass, eight-tab strip at 123/83 so 120 and 90 columns fit, and Perf methodology in contextual help. Verified with number-select 1-8, group-cycle reload, scope/legend/help tests, tab-strip fit at 120/90, and just test-scoped (1068 passed after escalation). just check lint otherwise green; Symvision private-import failures are pre-existing on HEAD (see PROPOSED FOLLOW-UP).

[2026-08-16T02:15:58Z · sase-mj.3] Registered Perf as the eighth Statistics view: VIEW_ORDER/labels/descriptions (Perf/Prf), grouping (subsystem/provider/workflow with reload), lazy load + stale-group worker guard, dimmed project chip with '· not applied', empty-view bypass, eight-tab strip at 123/83 so 120 and 90 columns fit, and Perf methodology in contextual help. Verified with number-select 1-8, group-cycle reload, scope/legend/help tests, tab-strip fit at 120/90, and just test-scoped (1068 passed after escalation). just check lint otherwise green; Symvision private-import failures are pre-existing on HEAD (see PROPOSED FOLLOW-UP).

[2026-08-16T02:17:08Z · sase-mj.3] Verified Perf as 8th Statistics view: numbered 0/1-8 select (9 ignored); group cycle on Perf reloads and updates scope chip; project chip dimmed with not applied; empty agent-run ranges still paint Perf; tab-strip 123/83 thresholds keep 120/90-col compact; help methodology section; scoped tests passed (1068, selection escalated). Placeholder body only; sase-mj.4 owns the real renderable.

[2026-08-16T02:19:47Z · sase-mj.3] Verified Perf as 8th Statistics view: numbered 0/1-8 select (9 ignored); group cycle on Perf reloads and updates scope chip; project chip dimmed with not applied; empty agent-run ranges still paint Perf; tab-strip 123/83 thresholds keep 120/90-col compact; help methodology section; scoped tests passed (1068, selection escalated). Placeholder body only; sase-mj.4 owns the real renderable.

[2026-08-16T02:21:38Z · sase-mj.3] PROPOSED FOLLOW-UP: beads close publish blocked by sase-mk stream rewrite of ancestor event 5 during any store mutation (integrity restore then raise).

## Dependencies

- **Depends on:** [sase-mj.2](sase-mj.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mj.4](sase-mj.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mj.3/README.md) | [sase-mj.3](sase-mj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9423e3`](https://github.com/sase-org/sase/commit/d9423e37a96e7f7bb7efdd88fca91820e913f7bd) | feat(ace): register Perf as the eighth Statistics view | [sase-mj.3](sase-mj.3.md) | 2026-08-15 22:25:24 EDT |
