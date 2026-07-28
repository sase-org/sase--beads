# Bead: sase-5l.13 — doctor: fix prettier false-drift messaging

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.13

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.13`
**Created:** 2026-07-08 05:15:03 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Repair the existing prettier signal (no new check). Broaden the deep optional-tool prettier description to state its real impact, and label the config.init false-drift case with a note like stale counts may be inflated: prettier missing so doctor skill-drift output is not misleading when prettier is absent (generated skill files render without deployed formatting). Add or adjust tests. See research section 12 and the epic plan design file.

## Notes

COMMIT: 2e7861a2f

## Dependencies

- **Depends on:** [sase-5l.12](sase-5l.12.md) ✓
- **Blocks:** [sase-5l.14](sase-5l.14.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.13/README.md) | [sase-5l.13](sase-5l.13.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`2e7861a`](https://github.com/sase-org/sase/commit/2e7861a2fe4ee80bbb5db832ce66c67c88f15bee) | fix(doctor): clarify prettier skill drift diagnostics (sase-5l.13) | [sase-5l.13](sase-5l.13.md) | 2026-07-08 21:17:53 |
