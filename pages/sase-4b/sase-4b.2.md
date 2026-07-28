# Bead: sase-4b.2 — Phase 2: Add Generated /bob\_dataview Skill

[Bead Pages](../README.md) / [sase-4b](README.md) / sase-4b.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4b.2`
**Created:** 2026-06-03 19:57:20 UTC · **Closed:** 2026-06-03 20:25:16 UTC
**Plan:** [202606/bob\_dataview\_reads.md](https://github.com/sase-org/sase--plans/blob/main/202606/bob_dataview_reads.md)

## Notes

COMMIT: a500f334e

[2026-07-27T19:12:13Z · sase-a1.6] [2026-06-03T20:23:03Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Added src/sase/xprompts/skills/bob_dataview.md with provider-neutral read-only bob dataview guidance; generated and applied provider skill targets for claude, codex, gemini, gemini/jetski, opencode, and qwen; added source-generation coverage in tests/main/test_init_skills_sources.py. Verification: sase skills init --dry-run --force; sase skills init --force --no-commit; targeted chezmoi apply for bob_dataview; sase skills list reports 14 sources, 80 current, 0 stale, 0 missing; .venv/bin/pytest tests/main/test_init_skills_sources.py; just check.

[2026-07-27T19:12:30Z · sase-a1.6] [2026-06-03T20:25:43Z · bryanbugyi34@gmail.com] (restored 2026-07-27) COMMIT: ec67e48e1

## Dependencies

- **Depends on:** [sase-4b.1](sase-4b.1.md) ✓
- **Blocks:** [sase-4b.3](sase-4b.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4b.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4b.2/README.md) | [sase-4b.2](sase-4b.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a500f33`](https://github.com/sase-org/sase/commit/a500f334ed4cbdc81ae250db9ccfe5a737220d4a) | feat: add bob dataview generated skill source (sase-4b.2) | [sase-4b.2](sase-4b.2.md) | 2026-06-03 20:25:51 |
