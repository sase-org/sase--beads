# Bead: sase-r.3 — DAG to wave plan to multi-prompt builder (pure library)

[Bead Pages](../README.md) / [sase-r](README.md) / sase-r.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 21:21:04 UTC · **Closed:** 2026-04-25 21:57:11 UTC
**Plan:** [202604/epic\_work\_automation.md](https://github.com/sase-org/sase--plans/blob/main/202604/epic_work_automation.md)

## Description

Implement build_epic_work_plan and render_multi_prompt in src/sase/bead/work.py. Cycle detection, cross-epic-blocker rejection, deterministic agent naming. Heavy unit tests using in-memory bead fixtures (re-use db.create_memory_db()): linear chain, diamond, independent fan-out, closed blockers don't gate, cycle raises. Snapshot test on the rendered multi-prompt for the diamond case so the %name/%w/#bd/... output is locked in.

## Notes

COMMIT: 4299fcef

## Dependencies

- **Blocks:** [sase-r.4](sase-r.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d430c6d`](https://github.com/sase-org/sase/commit/d430c6d7c467d9bcb27203caf45e24d403ff0262) | feat: DAG to wave plan to multi-prompt builder for epic work automation (sase-r.3) | [sase-r.3](sase-r.3.md) | 2026-04-25 21:57:15 |
