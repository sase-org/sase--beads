# Bead: sase-r1.6 — Retire the Admin Center auto-update path

[Bead Pages](../README.md) / [sase-r1](README.md) / sase-r1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.080](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.080.md) · **Assignee:** `sase-r1.6` · **Size:** medium
**Created:** 2026-08-19 12:05:16 EDT · **Closed:** 2026-08-19 17:01:22 EDT
**Plan:** [202608/update\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/update_panel.md)

## Description

retire: delete the auto_update and captured-provider plumbing that only existed for the old ,U dispatch, and drop the comprehensive mixin from the Updates pane.

## Notes

[2026-08-19T21:01:22Z · sase-r1.6] Retired the Admin Center auto-update path: dropped auto_update and comprehensive_provider_names from ConfigCenterModal, _open_config_center, the Updates pane factory, and pane workers; deleted ComprehensiveUpdateActionsMixin and its pane worker/incoming-commits handoff; kept pane u/A/a plus extracted preview/execution helpers (now private). just check green (fmt, lint including symvision, scoped tests 302/3072).

[2026-08-19T21:02:45Z · sase-r1.6] Retired Admin Center auto-update path: dropped auto_update and comprehensive_provider_names from ConfigCenterModal, _open_config_center, Updates pane factory, and pane workers; deleted ComprehensiveUpdateActionsMixin and pane worker/incoming-commits handoff; kept pane u/A/a plus extracted preview/execution helpers (now private). just check green (fmt, lint including symvision, scoped tests 302/3072). No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-r1.5](sase-r1.5.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r1.6/README.md) | [sase-r1.6](sase-r1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f191496`](https://github.com/sase-org/sase/commit/f1914962c8f7a5fb4bb9facc0888b70aa070d87b) | feat(ace): retire Admin Center auto-update plumbing | [sase-r1.6](sase-r1.6.md) | 2026-08-19 17:03:49 EDT |
