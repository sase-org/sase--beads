# Bead: sase-5l.8 — doctor: surface tools.fzf in top-level doctor

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.8

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.8`
**Created:** 2026-07-08 05:13:05 UTC · **Closed:** 2026-07-08 20:25:32 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a tools.fzf check to sase doctor (default if top-level doctor is first-run readiness, else deep) so it is not only in sase prompt doctor. WARN when missing. fzf gates prompt pickers and editor prompt history (the editor path in src/sase/main/query_handler/_editor.py prints an error when fzf is missing). Add tests. See research section 8 and the epic plan design file.

## Dependencies

- **Depends on:** [sase-5l.7](sase-5l.7.md) ✓
- **Blocks:** [sase-5l.9](sase-5l.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.8/README.md) | [sase-5l.8](sase-5l.8.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`35d813f`](https://github.com/sase-org/sase/commit/35d813fb2df084180bd70d353e7b422fd044071a) | feat(doctor): add fzf tool diagnostic (sase-5l.8) | [sase-5l.8](sase-5l.8.md) | 2026-07-08 07:29:24 |
