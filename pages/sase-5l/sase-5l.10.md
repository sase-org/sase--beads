# Bead: sase-5l.10 — doctor: add resources.chezmoi and config.skills.applied deep checks

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.10

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.10`
**Created:** 2026-07-08 05:13:57 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add two deep, conditional chezmoi checks. resources.chezmoi: SKIP unless use_chezmoi is true or the chezmoi source tree exists; ERROR when enabled but chezmoi is missing; WARN for suspicious source state. config.skills.applied: stat the real home skill targets and advise chezmoi apply when the chezmoi source and applied home state diverge (source can look current while applied copies are stale or missing). Add tests. See research section 9 and the epic plan design file.

## Notes

COMMIT: 1db06a547

## Dependencies

- **Blocks:** [sase-5l.11](sase-5l.11.md) ✓
- **Depends on:** [sase-5l.9](sase-5l.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.10/README.md) | [sase-5l.10](sase-5l.10.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1db06a5`](https://github.com/sase-org/sase/commit/1db06a547c618912538a50434fb646b933a7fe38) | feat(doctor): add deep chezmoi skill diagnostics (sase-5l.10) | [sase-5l.10](sase-5l.10.md) | 2026-07-08 20:39:16 |
