# Bead: sase-t2.2 — Python model, projections, and text consumers

[Bead Pages](../README.md) / [sase-t2](README.md) / sase-t2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ct](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ct.md) · **Assignee:** `sase-t2.2` · **Size:** medium
**Created:** 2026-08-24 14:37:56 EDT · **Closed:** 2026-08-25 06:43:05 EDT
**Plan:** [202608/timestamped\_bead\_notes.md](https://github.com/sase-org/sase--plans/blob/main/202608/timestamped_bead_notes.md)

## Description

pyapi: carry the structured note list through the Python `Issue` model, JSONL codec, SQLite mirror, and every read-only consumer via `notes_text`.

## Dependencies

- **Depends on:** [sase-t2.1](sase-t2.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-t2.3](sase-t2.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-t2.4](sase-t2.4.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.2/README.md) | [sase-t2.2](sase-t2.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f6c1467`](https://github.com/sase-org/sase/commit/f6c14672253185772692f4183e64f07c8df396a8) | feat(bead): carry structured notes through the Python model and read consumers | [sase-t2.2](sase-t2.2.md) | 2026-08-24 17:08:28 EDT |
| sase-core | [`sase-core@75eb619`](https://github.com/sase-org/sase-core/commit/75eb61989b173010b6f8dba23e10534867737ff7) | feat(bead): default the notes column to an empty structured list | [sase-t2.2](sase-t2.2.md) | 2026-08-24 17:10:57 EDT |
