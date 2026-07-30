# Bead: sase-b7.4 — Wire the policy into finalization capture

[Bead Pages](../README.md) / [sase-b7](README.md) / sase-b7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.4` · **Size:** small
**Created:** 2026-07-30 12:53:36 UTC · **Closed:** 2026-07-30 14:17:37 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

capture-wiring: label capture candidates with their origin, route them through the policy at finalization, write reference rows instead of byte copies, enforce the cap, and cover the decision matrix end to end.

## Notes

[2026-07-30T14:17:37Z · sase-b7.4] Implemented capture policy wiring into default artifact finalization; verified with just install, targeted artifact/publishing tests, and full just check.

## Dependencies

- **Depends on:** [sase-b7.2](sase-b7.2.md) ✓
- **Depends on:** [sase-b7.3](sase-b7.3.md) ✓
- **Blocks:** [sase-b7.5](sase-b7.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.4/README.md) | [sase-b7.4](sase-b7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`94daa1e`](https://github.com/sase-org/sase/commit/94daa1ebdcff2d3adf11c24599d04807f8a5a03a) | feat(artifacts): wire VCS-backed default capture | [sase-b7.4](sase-b7.4.md) | 2026-07-30 14:20:33 |
