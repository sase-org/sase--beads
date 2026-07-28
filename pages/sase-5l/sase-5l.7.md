# Bead: sase-5l.7 — doctor: add runtime.node conditional setup check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.7`
**Created:** 2026-07-08 05:12:18 UTC · **Closed:** 2026-07-08 20:25:32 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a default runtime.node check that WARNs only when node/npm is missing AND an npm-distributed provider (claude, codex, qwen use npm install -g per src/sase/doctor/checks_providers.py) is registered but its CLI is not found; otherwise SKIP or OK. Node is not a universal SASE requirement, so avoid unconditional warnings. Add tests. See research section 7 and the epic plan design file.

## Dependencies

- **Depends on:** [sase-5l.6](sase-5l.6.md) ✓
- **Blocks:** [sase-5l.8](sase-5l.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.7/README.md) | [sase-5l.7](sase-5l.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9ea0828`](https://github.com/sase-org/sase/commit/9ea0828c35d0a409737c107a152ac060b8b39465) | feat(doctor): add conditional node runtime check (sase-5l.7) | [sase-5l.7](sase-5l.7.md) | 2026-07-08 07:19:36 |
