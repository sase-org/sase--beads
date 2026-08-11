# Bead: sase-jd.5 — external\_pr\_mirror chop and the two-file Patch importer

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.5` · **Size:** large
**Created:** 2026-08-10 19:14:41 EDT · **Closed:** 2026-08-11 07:28:19 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

pr_mirror: add the per-project builtin chop that adopts unowned remote PRs as Patches, built on a new importer that locks the active and archive ProjectSpec files together and writes merged and closed PRs straight into the archive.

## Notes

[2026-08-11T11:28:19Z · sase-jd.5] Verified with just install, focused ruff/pytest/Rust tests, just check, just check-full, and git diff --check in main and linked sase-core.

## Dependencies

- **Depends on:** [sase-jd.2](sase-jd.2.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-jd.3](sase-jd.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.5.md) | [sase-jd.5](sase-jd.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f5aa4d1`](https://github.com/sase-org/sase-core/commit/f5aa4d1d7c5b30699407192866d309cdc2f08967) | feat(external-pr): classify external pull request imports | [sase-jd.5](sase-jd.5.md) | 2026-08-11 07:29:34 EDT |
