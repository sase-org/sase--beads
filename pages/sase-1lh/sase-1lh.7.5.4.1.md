# Bead: sase-1lh.7.5.4.1 — Bound every subprocess exit path and declare the intended release version

[Bead Pages](../README.md) / [sase-1lh.7.5.4](sase-1lh.7.5.4.md) / sase-1lh.7.5.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.land.md) · **Assignee:** `sase-1lh.7.5.4.1` · **Size:** medium
**Created:** 2026-10-16 23:11:55 EDT · **Closed:** 2026-10-16 23:37:36 EDT
**Plan:** [202610/finish\_deadline\_release\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_deadline_release_target.md)

## Description

deadline-repair: fix early-EOF waits and surviving descendants, add bounded regressions, and include Release-As: 0.18.0 in the host commit declaration.

## Notes

[2026-10-17T03:37:12Z · sase-1lh.7.5.4.1] HOST COMMIT DECLARATION: include a separate footer line `Release-As: 0.18.0` in the host-created primary commit for this repair. The release-watch phase must verify that exact trailer in the committed SHA before any release PR regeneration.

[2026-10-17T03:37:20Z · sase-1lh.7.5.4.1] PROPOSED FOLLOW-UP: Existing task sase-1lm tracks the same Python-version-dependent argparse docs-gen-check drift and records clean-base reproductions. This run’s sase tool run check failed only at docs-gen-check under Python 3.14.7 with generated CLI usage diffs; this phase changed only visual maintenance code/tests and did not change CLI generation or docs/reference/cli, so do not duplicate the task.

[2026-10-17T03:37:36Z · sase-1lh.7.5.4.1] Fixed EOF deadline enforcement and process-group escalation for surviving descendants; added bounded subprocess and check-mode regressions. 135 focused maintenance/workflow tests passed and just fix completed. sase tool run check failed only at the existing Python-version-dependent docs-gen-check drift tracked by sase-1lm; phase epic-symbols is empty. Recorded Release-As: 0.18.0 for the host commit and release-watch verification.

## Dependencies

- **Blocks:** [sase-1lh.7.5.4.2](sase-1lh.7.5.4.2.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.4.1/README.md) | [sase-1lh.7.5.4.1](sase-1lh.7.5.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69e0cd7`](https://github.com/sase-org/sase/commit/69e0cd75400465a1433717bad5e8e623379814c8) | fix(tui): bound visual subprocess cleanup | [sase-1lh.7.5.4.1](sase-1lh.7.5.4.1.md) | 2026-10-16 23:38:46 EDT |
