# Bead: sase-5l.4 — doctor: add tools.editor shared editor resolver and check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.4`
**Created:** 2026-07-08 05:11:00 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Create one shared editor resolver and reuse it from doctor and the editor call sites (src/sase/workflows/commit/editor_utils.py, src/sase/main/query_handler/_editor.py, src/sase/ace/tui/actions/agent_workflow/_editor.py). Add a default tools.editor check: OK when VISUAL/EDITOR or nvim/vim resolves; WARN when the selected command head is missing or only an unverified shell command was configured. Support commands like code --wait as valid. Add tests. See research section 4 and the epic plan design file.

## Notes

COMMIT: ea7a8898e

## Dependencies

- **Depends on:** [sase-5l.3](sase-5l.3.md) ✓
- **Blocks:** [sase-5l.5](sase-5l.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.4/README.md) | [sase-5l.4](sase-5l.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a788d8c`](https://github.com/sase-org/sase/commit/a788d8cbe44da8be000748943a1914e4c320942b) | feat(doctor): add editor command diagnostic (sase-5l.4) | [sase-5l.4](sase-5l.4.md) | 2026-07-08 06:38:26 |
