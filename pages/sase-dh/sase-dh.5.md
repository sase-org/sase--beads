# Bead: sase-dh.5 — Validation for the canonical prompt archive

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.5` · **Size:** medium
**Created:** 2026-08-01 15:07:34 UTC · **Closed:** 2026-08-01 18:42:31 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

validate: add sase agent prompts validate, teach plan links validate about cross-repo prompt links, and wire the new check into sase validate.

## Notes

[2026-08-01T18:37:26Z · sase-dh.5] PROPOSED FOLLOW-UP: Repair malformed uppercase_active_subtabs SDD pair — just check currently reports reverse-link and discontiguous-header link-format errors for 202607/prompts/uppercase_active_subtabs.md; the plans sidecar was clean and this phase did not modify it.

[2026-08-01T18:42:31Z · sase-dh.5] Verified sase agent prompts list/show/validate CLI wiring and default-list behavior; all six prompt archive diagnostic codes with clean/missing-counterpart cases; absolute hosted PROMPT handling plus prompt-in-plans-store warnings; top-level sase validate aggregation. just lint passed, 144 affected subsystem tests passed, CLI smoke passed, and the new agent prompts validate check passed inside just check. just check remains blocked only by the unrelated pre-existing uppercase_active_subtabs SDD link errors recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-dh.4](sase-dh.4.md) ✓
- **Blocks:** [sase-dh.6](sase-dh.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.5/README.md) | [sase-dh.5](sase-dh.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`64c26f1`](https://github.com/sase-org/sase/commit/64c26f106fac8b03237761f420079fae71c116b3) | feat(agent): add canonical prompt archive validation | [sase-dh.5](sase-dh.5.md) | 2026-08-01 18:44:18 |
