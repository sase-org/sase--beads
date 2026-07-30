# Bead: sase-b7.3 — Python record, doctor, and read surfaces

[Bead Pages](../README.md) / [sase-b7](README.md) / sase-b7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.3` · **Size:** medium
**Created:** 2026-07-30 12:53:29 UTC · **Closed:** 2026-07-30 13:47:09 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

py-record: mirror the new record fields in Python, make ids and dedupe keys work without a stored path, teach doctor that byte-free rows are healthy, and make every read surface materialize VCS-backed content on demand.

## Notes

[2026-07-30T13:47:09Z · sase-b7.3] Implemented Python VCS-backed artifact records, stable ids/dedupe, reference-mode writes, doctor/query/schema updates, content-verified materialization across CLI/prompt/Files-pane reads, multi-checkout resolver context, and regression coverage. Verified 153 focused tests pass; ruff and mypy pass; full just test reached 24,220 passed/7 skipped with one unrelated Agents slow-tool visual timing failure that passed isolated via just test-visual. just check passes every format/lint gate and stops only at pre-existing missing reciprocal prompt links for the epic design in the SDD sidecar.

## Dependencies

- **Depends on:** [sase-b7.1](sase-b7.1.md) ✓
- **Blocks:** [sase-b7.4](sase-b7.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.3/README.md) | [sase-b7.3](sase-b7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`c9edec5`](https://github.com/sase-org/sase/commit/c9edec56145a050d89ed18911c27f90831e7a9dc) | feat(artifacts): materialize VCS-backed files on demand | [sase-b7.3](sase-b7.3.md) | 2026-07-30 13:48:54 |
