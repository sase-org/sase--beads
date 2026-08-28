# Bead: sase-um.9.2 — Drive Full CI green

[Bead Pages](../README.md) / [sase-um.9](sase-um.9.md) / sase-um.9.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.land.md) · **Assignee:** `sase-um.9.2` · **Size:** medium
**Created:** 2026-08-28 15:48:59 EDT
**Plan:** [202608/release\_gate\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md)

## Description

heavy: fix the three drifted ACE PNG goldens that reproduce deterministically on the tip, attribute the test (3.13) and coverage-contexts failures that pass serially, and confirm a completed Full CI run is green.

## Notes

[2026-08-28T21:11:53Z · sase-um.9.2] PROPOSED FOLLOW-UP: Refresh generated SASE memory/provider shims — `just check` fails `sase validate` because `init memory --check` reports stale generated SASE memory files and provider shims under the home/chezmoi memory output; needs owner-authorized memory regeneration.

[2026-08-28T21:16:36Z · sase-um.9.2] STATUS: Visual repair complete and verified with `just test-visual` (842 passed, 1 skipped); targeted non-visual attribution nodes pass locally, under py313 for the ACE checkout test, and under `just test-contexts` for the three coverage-contexts nodes. Not closing yet because the post-pin `just check` rerun is blocked by generated SASE memory/provider-shim drift and no completed green Full CI run includes this repair.

## Dependencies

- **Blocks:** [sase-um.9.4](sase-um.9.4.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.2/README.md) | [sase-um.9.2](sase-um.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed74b9f`](https://github.com/sase-org/sase/commit/ed74b9f7b742e4e252ef6693cdd9096711cb2958) | test: stabilize full ci release gate | [sase-um.9.2](sase-um.9.2.md) | 2026-08-28 17:18:10 EDT |
