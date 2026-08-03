# Bead: sase-em.5 — Artifact-file calendar dates in the configured timezone

[Bead Pages](../README.md) / [sase-em](README.md) / sase-em.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sn/README.md) · **Assignee:** `sase-em.5` · **Size:** medium
**Created:** 2026-08-03 07:46:14 EDT
**Plan:** [202608/timezone\_display\_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)

## Description

artifact-dates: mint artifact `created_at` and the retention `now` with the configured-tz offset and make the Rust core bucket calendar dates by that embedded offset, so `date:`/`since:` filtering agrees with the displayed day.

## Notes

[2026-08-03T13:29:18Z · sase-em.5] PROPOSED FOLLOW-UP: Backfill legacy artifact created_at offsets — sase artifact doctor --fix only fills missing digest, size, and MIME enrichment and does not refresh created_at when file mtime changes, so existing +00:00 rows keep UTC calendar-day bucketing until separately re-indexed; consider a one-shot mtime-derived configured-timezone backfill.

[2026-08-03T13:31:25Z · sase-em.5] PROPOSED FOLLOW-UP: Remove stale sase-ej Symvision epic-symbol exemptions — just check reports enqueue_bead_pages_publication, enqueue_committed_agent_publication, enqueue_plan_header_publication, and enqueue_sidecar_push_publication are already properly used, so their exemptions now make the required check fail before tests.

[2026-08-03T13:31:55Z · sase-em.5] PROPOSED FOLLOW-UP: Remove stale sase-ej Symvision epic-symbol exemptions — just check reports enqueue_bead_pages_publication, enqueue_committed_agent_publication, enqueue_plan_header_publication, and enqueue_sidecar_push_publication are already properly used, so their exemptions now make the required check fail before tests.

[2026-08-03T13:45:48Z · sase-em.5] PROPOSED FOLLOW-UP: Refresh or repair Config Center Agent CLI PNG goldens — full just test and an isolated just test-visual rerun both reproduce mismatches for config_center_agent_clis_marked_120x40 (0.670357% changed) and config_center_agent_clis_update_preview_120x40 (0.281415% changed); this phase does not touch Config Center rendering or those fixtures.

## Dependencies

- **Depends on:** [sase-em.1](sase-em.1.md) ✓
- **Blocks:** [sase-em.6](sase-em.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-em.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-em.5/README.md) | [sase-em.5](sase-em.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e153a2e`](https://github.com/sase-org/sase-core/commit/e153a2ea40675cc6e3ab10ad966f9be875f26e4d) | fix(artifacts): honor embedded offsets for calendar dates | [sase-em.5](sase-em.5.md) | 2026-08-03 09:47:39 EDT |
| sase | [`eda7c15`](https://github.com/sase-org/sase/commit/eda7c1564387abf356e601dd32d86c68b4efedd8) | fix(artifacts): mint timestamps in the configured timezone | [sase-em.5](sase-em.5.md) | 2026-08-03 09:48:30 EDT |
