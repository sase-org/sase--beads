# Bead: sase-em.2 — Artifacts tab and artifact CLI

[Bead Pages](../README.md) / [sase-em](README.md) / sase-em.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sn/README.md) · **Assignee:** `sase-em.2` · **Size:** medium
**Created:** 2026-08-03 11:45:19 UTC
**Plan:** [202608/timezone\_display\_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)

## Description

artifacts: fix the Files/Beads/Plans panes, the artifact-ref completion menu, and `sase artifact list` so artifact and bead timestamps render in the configured timezone instead of raw UTC.

## Notes

[2026-08-03T13:08:58Z · sase-em.2] PROPOSED FOLLOW-UP: Remove stale sase-ej Symvision epic-symbol entries — just check reports enqueue_bead_pages_publication, enqueue_committed_agent_publication, enqueue_plan_header_publication, and enqueue_sidecar_push_publication are already properly used, so their Justfile entries should be removed.

[2026-08-03T13:33:09Z · sase-em.2] PROPOSED FOLLOW-UP: Refresh or diagnose two Config Center Agent CLI PNG goldens — test_config_center_agent_clis_marked_png_snapshot and test_config_center_agent_clis_update_preview_png_snapshot mismatch consistently in the full suite and when rerun alone; they are unrelated to artifact timestamp rendering.

[2026-08-03T13:33:45Z · sase-em.2] PROPOSED FOLLOW-UP: Harden the bead mutation contention regression under loaded parallel runs — test_concurrent_bead_mutations_wait_past_the_old_lock_timeout exceeded its 12s lock deadline in the full suite but passed alone in 3.64s.

## Dependencies

- **Depends on:** [sase-em.1](sase-em.1.md) ✓
- **Blocks:** [sase-em.6](sase-em.6.md) ◐
