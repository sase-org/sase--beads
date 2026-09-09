# Bead: sase-yh.5.2 — Preserve unpublished sidecars under retry and configuration drift

[Bead Pages](../README.md) / [sase-yh.5](sase-yh.5.md) / sase-yh.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yh.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yh.land.md) · **Assignee:** `sase-yh.5.2` · **Size:** medium
**Created:** 2026-09-09 07:14:15 EDT · **Closed:** 2026-09-09 08:35:31 EDT
**Plan:** [202609/stitch\_recovery\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/stitch_recovery_landing_repairs.md)

## Description

publication-preservation: make missing upstream an explicit failure, prevent mismatched-remote discovery or later store resolution from replacing unpublished clones, bound every probe and lock by the chop deadline, rotate retry roots fairly, and add the missing restart, aging, drift, contention, ownership, and deadline regressions.

## Notes

[2026-09-09T12:35:31Z · sase-yh.5.2] Implemented missing-upstream diagnostics, non-destructive hidden-clone publication guards, deadline plumbing, retry rotation, and regressions; verified just fmt, git diff --check, focused pytest, just _lint-symvision, and just check.

## Dependencies

- **Blocks:** [sase-yh.5.3](sase-yh.5.3.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yh.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yh.5.2/README.md) | [sase-yh.5.2](sase-yh.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a1b08d0`](https://github.com/sase-org/sase/commit/a1b08d06c9b0419c96d91b76f8dc77a78bee82a0) | fix(sdd): preserve unpublished artifact sidecars | [sase-yh.5.2](sase-yh.5.2.md) | 2026-09-09 08:37:10 EDT |
