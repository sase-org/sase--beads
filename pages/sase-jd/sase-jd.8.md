# Bead: sase-jd.8 — Retire Bugs, rename PRs to Patches, reorder the Artifacts sub-tabs

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.8` · **Size:** large
**Created:** 2026-08-10 19:15:10 EDT · **Closed:** 2026-08-11 11:08:17 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

tabs: collapse the Artifacts sub-tabs to Stitches, Patches, Beads, Files by deleting the Bugs pane and renaming the prs identifier to patches, keeping deprecated action aliases, and regenerating every affected text and PNG golden.

## Notes

[2026-08-11T15:08:17Z · sase-jd.8] Landed plan retire_bugs_rename_prs_to_patches.md end to end. Verified: rg -n '"bugs"|artifacts_bugs|artifacts-bugs|ArtifactsBugsPane|"prs"|artifacts-prs|ArtifactsPrsPane' src/ returns only the deliberate compat aliases (LEGACY_ARTIFACTS_SUBTABS, action_show_artifacts_bugs/_prs, the catalog 'prs' alias, artifact_ref_entries generic kind map). just install; mypy (2992 files, 0 issues incl. a real catalog.py tuple-type fix); ruff check + format (clean, one pre-existing unrelated fmt issue in tests/test_external_mirror_issues.py confirmed present at HEAD, untouched); symvision (clean after deleting dead find_bug_links/BugLinks/_normalize_bug_id from src/sase/bug_links.py and privatizing ExternalRefLinks, plus deleting dead issue_url from external_issues.py -- orphaned by the pane deletion, not called out by the plan's file list but required by the symvision gate); keep-sorted, changelog, patch/stitch terminology, toobig, validate, validate-committed-plans all clean. just test-scoped: 28895 passed twice (0 failures) after fixing ~24 test files the plan's Step 4 sweep missed (mostly stale 1-5 digit-key assumptions from the old Stitches/Beads/Bugs/PRs/Files order, done via 4 parallel subagents + my own audit). just test-visual: 650 passed after the same digit fix applied across tests/ace/tui/visual/ (audited every occurrence for context correctness, caught and reverted one false-positive sed hit on an unrelated Agents-tab lane-jump key) and --sase-update-visual-snapshots to accept the intentional tab-strip relabeling (eyeballed diff.png for 5+ samples across unrelated categories before bulk-accepting). just test-cost and just selection-health --fail-on-new-flake both passed (exit 0); the one flake observed (test_logs_tab_g_and_shift_g_scroll_detail_extremes) is pre-existing/untouched and already tracked at sase-jb, which I +1'd.

## Dependencies

- **Depends on:** [sase-jd.4](sase-jd.4.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-jd.6](sase-jd.6.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.8.md) | [sase-jd.8](sase-jd.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b5786b5`](https://github.com/sase-org/sase/commit/b5786b57f22a316af7edb5fc35789b65672d96c7) | feat(ace)!: retire the Bugs sub-tab and rename Artifacts PRs to Patches | [sase-jd.8](sase-jd.8.md) | 2026-08-11 11:36:05 EDT |
