# Bead: sase-5l.3 — doctor: add resources.disk\_free check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.3`
**Created:** 2026-07-08 05:10:43 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a default resources.disk_free diagnostic in a new resources check group. ERROR when the workspace root has under ~1 GB free; WARN under ~3 GB; OK otherwise. Include sase_home as a secondary path. Next steps: free space or run sase workspace cleanup; note live workspaces can consume hundreds of MB to over 1 GB after checkout and .venv creation. Rationale: numbered workspaces are real git clones (_ensure_git_clone_at raises on failure), so a full disk hard-fails agent launch even though state.paths reports writable. Add tests. See research section 3 and the epic plan design file.

## Notes

COMMIT: 26c9ed9d3

## Dependencies

- **Depends on:** [sase-5l.2](sase-5l.2.md) ✓
- **Blocks:** [sase-5l.4](sase-5l.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.3/README.md) | [sase-5l.3](sase-5l.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`df19d58`](https://github.com/sase-org/sase/commit/df19d586b53cd0db2f63d512178ff43e5ced770f) | feat(doctor): add disk resource diagnostic (sase-5l.3) | [sase-5l.3](sase-5l.3.md) | 2026-07-08 06:17:51 |
