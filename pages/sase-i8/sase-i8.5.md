# Bead: sase-i8.5 — Marking merges in every renderer

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.5` · **Size:** medium
**Created:** 2026-08-09 09:43:53 EDT · **Closed:** 2026-08-09 13:44:59 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

render: give merges a dedicated accent, a reserved marker column that costs nothing when no merge is visible, a legend key, parent lines in full output, structured JSON fields, and a condensed pull-request headline in the pretty timeline.

## Notes

[2026-08-09T17:44:59Z · sase-i8.5] Implemented merge markers, merge legend, full-format parent lines, JSON merge fields, pretty timeline PR headline condensation, and stale Symvision whitelist cleanup; verified with .venv/bin/pytest tests/test_vcs_log_render_pretty.py tests/test_vcs_log_render_full.py tests/test_vcs_log_render_compact.py, just _lint-symvision, and just check (scoped lane escalated to full suite and passed).

[2026-08-09T17:46:22Z · sase-i8.5] .venv/bin/pytest tests/test_vcs_log_render_pretty.py tests/test_vcs_log_render_full.py tests/test_vcs_log_render_compact.py; just _lint-symvision; just check passed (scoped lane escalated to full suite and passed).

## Dependencies

- **Depends on:** [sase-i8.4](sase-i8.4.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.7](sase-i8.7.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.5/README.md) | [sase-i8.5](sase-i8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`77ee670`](https://github.com/sase-org/sase/commit/77ee67052e418c7825249cb95ca1f32fe55f6b40) | feat(vcs-log): mark merge commits in renderers | [sase-i8.5](sase-i8.5.md) | 2026-08-09 13:47:40 EDT |
