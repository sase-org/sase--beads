# Bead: sase-jd.3 — PR\_ORIGIN field, SASE\_PATCH stamp, and the external-Patch safety exclusion

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.3` · **Size:** medium
**Created:** 2026-08-10 19:14:03 EDT · **Closed:** 2026-08-10 20:02:41 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

pr_origin: add the tri-state PR_ORIGIN Patch field across parser, storage, section order, and the four ACE styling surfaces; stamp SASE_PATCH in append_pr_tags; and structurally exclude external Patches from AXE work before any importer can create one.

## Notes

[2026-08-10T23:43:06Z · sase-jd.3] PROPOSED FOLLOW-UP: Remove stale Symvision epic-symbol override — just check fails because --epic-symbol sase-j3(SnippetTriggerMatch) points at closed bead sase-j3.

[2026-08-10T23:43:49Z · sase-jd.3] PROPOSED FOLLOW-UP: Restore PR_ORIGIN Vim syntax styling surface — linked chezmoi checkout lacks home/dot_config/nvim/syntax/saseproject.vim or an obvious generated source for this plan item.

[2026-08-11T00:00:11Z · sase-jd.3] PROPOSED FOLLOW-UP: Fix keymap registry test/config conflict — test_stitches_action_override_wins_over_legacy_commits_alias expects stitches_next=minus, but minus conflicts with collapse_panel_folds and the registry reverts it to j.

[2026-08-11T00:02:41Z · sase-jd.3] Implemented PR_ORIGIN tri-state parsing/storage/wire/display, SASE_PATCH PR footer stamping, and AXE external-Patch exclusion. Verified focused pytest set: 118 passed; linked sase-core cargo test --workspace passed; just check passed fmt/ruff/mypy/terminology gates but is blocked by pre-existing stale Symvision epic-symbol sase-j3(SnippetTriggerMatch), with proposed follow-up notes recorded.

[2026-08-11T00:03:46Z · sase-jd.3] Implemented PR_ORIGIN parsing/storage/wire/rendering, PR SASE_PATCH footer stamping, and AXE external-origin exclusion; verified cargo test --workspace in linked sase-core passed, focused pytest passed with 118 tests, and just check reached the known unrelated Symvision stale epic-symbol blocker.

## Dependencies

- **Blocks:** [sase-jd.5](sase-jd.5.md) ◐ · ⧖ 2026-08-10
- **Blocks:** [sase-jd.7](sase-jd.7.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.3/README.md) | [sase-jd.3](sase-jd.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d0eeb48`](https://github.com/sase-org/sase-core/commit/d0eeb48324845c9d4ae946297a6b9e2d01c85c47) | feat: add Patch PR origin to core wire | [sase-jd.3](sase-jd.3.md) | 2026-08-10 20:05:45 EDT |
| sase | [`2951403`](https://github.com/sase-org/sase/commit/2951403192bb77aa7f8a9d376684f4fcf796885a) | feat: track Patch PR origin | [sase-jd.3](sase-jd.3.md) | 2026-08-10 20:07:19 EDT |
