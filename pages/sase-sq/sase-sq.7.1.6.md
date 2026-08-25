# Bead: sase-sq.7.1.6 — Migrate the sase and bob-cli trees

[Bead Pages](../README.md) / [sase-sq.7.1](sase-sq.7.1.md) / sase-sq.7.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.6` · **Size:** medium
**Created:** 2026-08-24 18:15:38 EDT · **Closed:** 2026-08-24 22:23:03 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

trees: run the migration for the sase project and the bob-cli project, regenerate memory in both, and prove the roster is byte-identical, closures match, and `sase memory init --check` is clean for sase, bob-cli, and home.

## Notes

[2026-08-25T01:54:06Z · sase-sq.7.1.6--2] PROPOSED FOLLOW-UP: Bead notes output golden drift — just test-scoped currently fails 7 bead CLI golden/search tests because notes render as arrays/notes_text and compact search no longer includes the expected owner label; this is outside the glossary web migration files.

[2026-08-25T02:16:40Z · sase-sq.7.1.6--3] PROPOSED FOLLOW-UP: Bead notes history output drift — just check-full also fails tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable because history note revision output no longer matches the pinned timestamp/author text; this is outside the glossary web migration files.

[2026-08-25T02:23:03Z · sase-sq.7.1.6--3] Verified glossary web migration for sase and bob-cli: clean memory init --check for sase, bob-cli, linked chezmoi, and home chezmoi; no phase epic-symbol leftovers; focused glossary source test passes and just check clears lint/SASE validation before failing only in unrelated bead notes-output drift recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-sq.7.1.4](sase-sq.7.1.4.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sq.7.1.5](sase-sq.7.1.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.1.6.md) | [sase-sq.7.1.6](sase-sq.7.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df95621`](https://github.com/sase-org/sase/commit/df956212be2c5c246cb45207c753623b3ca92f5e) | feat(memory): migrate sase glossary to web | [sase-sq.7.1.6](sase-sq.7.1.6.md) | 2026-08-24 22:24:33 EDT |
