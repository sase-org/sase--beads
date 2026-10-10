# Bead: sase-1jc.8 — Stabilize publication formats and service contracts

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.8` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT · **Closed:** 2026-10-10 12:08:22 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

publication-services: Follow phase 8 and the shared removal checklist. Retire slim_agents_manifest, agents_session_manifest_compat, bgcmd_legacy_slots, and axe_routine_job_contract; close sase-11p, sase-1ft, sase-13w, and sase-11f. Write only slim manifests and canonical routine/job output; retain enabled explicit-file-set compatibility and legacy slot reading/actions. Preserve data-integrity checks and existing accepted input normalization.

## Notes

[2026-10-10T14:54:11Z · sase-1jc.8] PROPOSED FOLLOW-UP: Update sase/memory/macros.md to describe typed Proc launches as unconditional (skipped per epic macro_memory=no decision)

[2026-10-10T14:54:23Z · sase-1jc.8] PROPOSED FOLLOW-UP: Update sase/memory/tui_perf.md rule 14 to describe refresh tokens as unconditional while preserving performance requirements (skipped per epic refresh_memory=no decision)

[2026-10-10T16:08:10Z · sase-1jc.8--1] PROPOSED FOLLOW-UP: Full `sase tool run check` (run 4c112ee1f8f4a93c202b1d357388cf1a via monitor 72cqjdd63jf4) timed out at 1h during the test phase after all lint/SASE-validation/committed-plans stages passed; only staged failure was the KNOWN symvision ArtifactIndexProjection item. Land agent may re-run full check when host capacity allows.

[2026-10-10T16:08:22Z · sase-1jc.8--1] Phase 8 done: retired slim_agents_manifest, agents_session_manifest_compat, bgcmd_legacy_slots, axe_routine_job_contract (29 files). Verified: 148/148 touched pytest files pass; sase-core 36 config_parity + 64 config unit + 24 provenance pass; full check lint/SASE-validation/committed-plans green, only KNOWN symvision ArtifactIndexProjection (file untouched by this phase); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1jc.7](sase-1jc.7.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.9](sase-1jc.9.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.8.md) | [sase-1jc.8](sase-1jc.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9573108`](https://github.com/sase-org/sase-core/commit/9573108dac5dbb5223c05d3c4c1c2f0613b8b2c9) | feat(config): retire legacy axe/config wires in sase-core for publication-services flags | [sase-1jc.8](sase-1jc.8.md) | 2026-10-10 12:09:40 EDT |
