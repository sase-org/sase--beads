# Bead: sase-yy.6 — Fence, import legacy indexes, and cut over

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.6` · **Size:** large
**Created:** 2026-09-09 11:48:19 EDT · **Closed:** 2026-09-10 11:58:22 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

cutover-import: one-shot deterministic import of frozen legacy indexes into baseline events, flag enablement and removal, read-only legacy indexes, doctor guardrails, and re-pointing the publication retry lane's legacy-index discovery at the event lane.

## Notes

[2026-09-10T15:57:54Z · sase-yy.6] PROPOSED FOLLOW-UP: Close flag task bead sase-z0 after land-owner review; this phase removed the code-level link_events flag, the config schema entry, and legacy branches.

[2026-09-10T15:58:22Z · sase-yy.6] Implemented artifact-link cutover import: strict STORE markers, import-indexes CLI, event-only writers/drain, doctor checks, and link_events removal. Verification: just check passed; scoped pytest bundle passed with 173 tests.

## Dependencies

- **Depends on:** [sase-yy.1](sase-yy.1.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yy.4](sase-yy.4.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yy.5](sase-yy.5.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.7](sase-yy.7.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.6.md) | [sase-yy.6](sase-yy.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a8d99d2`](https://github.com/sase-org/sase/commit/a8d99d2952681d2aed4e755a30942e8cc82a0424) | feat(artifact-links): cut over legacy indexes to events | [sase-yy.6](sase-yy.6.md) | 2026-09-10 13:34:12 EDT |
