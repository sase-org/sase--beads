# Bead: sase-dh.6 — Migrate historical prompts out of the plans sidecar

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.6` · **Size:** medium
**Created:** 2026-08-01 15:08:06 UTC · **Closed:** 2026-08-01 19:21:25 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

migrate: move every existing <YYYYMM>/prompts/*.md into the agents sidecar, repair both link directions, and leave the plans sidecar with zero prompt files.

## Notes

[2026-08-01T19:20:47Z · sase-dh.6] PROPOSED FOLLOW-UP: Reconcile home SASE memory initialization drift — sase validate passes plan and prompt checks, but init memory --check reports seven generated chezmoi memory/provider shim files out of date.

[2026-08-01T19:20:59Z · sase-dh.6] PROPOSED FOLLOW-UP: Restrict Rust plan-header detection to the leading header block — ordinary body bullets such as **Artifacts:** are currently misclassified as discontiguous header sections.

[2026-08-01T19:21:25Z · sase-dh.6] Verified 2,892 historical prompts migrated across 202603–202608; the plans sidecar has zero prompt files, the agents archive validates 2,893 prompts with zero errors or warnings, and plan links validate 3,392 plans with zero errors. A repeat migration is a clean no-op. just lint and 48 focused phase tests pass. just check reaches aggregate validation but is blocked only by pre-existing home memory initialization drift; the full suite's remaining failures belong to concurrently landed unrelated work. Proposed follow-ups were recorded for both findings.

## Dependencies

- **Depends on:** [sase-dh.5](sase-dh.5.md) ✓
- **Blocks:** [sase-dh.7](sase-dh.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.6/README.md) | [sase-dh.6](sase-dh.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`fa7e7c8`](https://github.com/sase-org/sase/commit/fa7e7c8a7d58ca15e3a9e906ae90f7e4959972a3) | feat(agent)!: migrate prompts to the agents archive | [sase-dh.6](sase-dh.6.md) | 2026-08-01 19:23:14 |
