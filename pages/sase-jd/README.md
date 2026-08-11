# Bead: sase-jd — Mirror external issues into beads and external PRs into Patches

[Bead Pages](../README.md) / sase-jd

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.land`
**Created:** 2026-08-10 19:13:02 EDT · **Closed:** 2026-08-11 13:22:22 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

Every issue in an enabled project's external tracker has a corresponding bead and every PR not created by SASE's tracked workflow has a corresponding Patch, kept current continuously by AXE on every enabled project on the machine, and the Artifacts tab presents those relationships on one integrated surface whose sub-tabs are Stitches, Patches, Beads, Files.

## Notes

[2026-08-11T11:53:51Z · xw] DISCOVERED ISSUE: this workspace's built sase_core_rs floor (0.24.0) is missing 2 capabilities that this epic's own sase-core changes require: 'bead_external_ref_migration_sql' and 'bead_needs_external_ref_migration' (names strongly suggest phase sase-jd.1's external_ref bead identity field / SQL migration). Evidence: tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name fails with 'assert missing == []' -> ['bead_external_ref_migration_sql', 'bead_needs_external_ref_migration'], and just check's core-floor-probe step reports 'blocked_unpublished: sase-core-rs==0.24.0 is missing 2 capability(s), and at least one has no containing sase-core release tag yet.' Confirmed pre-existing and unrelated to my own change (an unrelated ACE prompt *-search feature) by stashing all edits incl. untracked files and rerunning against clean HEAD 1e8b37362 -- fails identically. Same stale-core-floor pattern as sase-d7/sase-h0/sase-hz/sase-ic/sase-jj, but distinct from those: at least one of these two capabilities has NO containing sase-core release tag yet, so a floor bump alone cannot fix it until sase-core cuts a release containing it. No new task bead filed; this active epic causally owns the missing capability and can raise the floor once sase-core publishes a release containing it.

[2026-08-11T12:22:59Z · toobig-2e.split_file.src.sase.axe.run_agent_exec_plan_accept.0] DISCOVERED ISSUE: During direct fallback verification for an unrelated accepted-plan module split on 2026-08-11, '.venv/bin/ruff format --check src/ tests/' found tests/test_external_mirror_issues.py unformatted at the read_mirror_state calls around lines 293 and 381 (the file is unchanged in this workspace's git status). This is causally within active epic sase-jd's external-issue mirror scope; I left the unrelated file untouched and did not create a task bead.

[2026-08-11T16:54:12Z · audit_bugs.sase.8] DISCOVERED ISSUE: On clean master eadb54323, just check-full fails deterministically at mypy with 21 errors in untouched post-c63b32 external-mirror code. src/sase/external_mirror/pull_requests.py imports missing ImportedPatch/import_patch/repair_patch_pr_association, ExternalMirrorConfig/get_external_mirror_config, and state helpers; it also constructs MirrorCursor with stale keyword names. src/sase/doctor/checks_deep_vcs_pull_requests.py imports missing compose_chop_subprocess_env. git log c63b32..HEAD attributes these paths to epic commits bdf21713a/265fdbed8/eadb54323. A focused ruff+mypy run for the unrelated notification-gate audit fix passes; no external-mirror files were changed.

[2026-08-11T17:13:09Z · toobig-2g.split_file.tests._test_cost.0] DISCOVERED ISSUE CORROBORATION: On HEAD eadb543235 after a fresh just install, unrelated tests/_test_cost module-splitting verification reached mypy and reproduced the same deterministic 21 errors: 20 in src/sase/external_mirror/pull_requests.py (missing importer/config/state exports plus stale MirrorCursor kwargs) and 1 in src/sase/doctor/checks_deep_vcs_pull_requests.py (missing compose_chop_subprocess_env). Ruff formatting and lint passed first; focused cost tests passed 28/28. No external-mirror files were changed.

[2026-08-11T17:22:22Z · sase-jd.land] LANDED epic sase-jd after verifying all 8 phases against source and the epic's commits, and fixing 3 defects the phases left behind.

VERIFIED COMPLETE: phase 1 external_ref bead identity field + partial-unique index (sase-core); phase 2 PullRequestWire/vcs_list_pull_requests provider seam; phase 3 PR_ORIGIN tri-state parsing/storage/wire/display + SASE_PATCH footer stamp + AXE external-Patch exclusion; phase 4 external_issue_mirror chop; phase 5 external_pr_mirror chop + two-file Patch importer; phase 6 external-issue presentation/actions in Beads pane (doctor checks registered via doctor/runner.py:90 -> external_pr_mirror_check_specs); phase 7 PR badge + origin chip; phase 8 sub-tabs collapsed to Stitches/Patches/Beads/Files. CLI surface confirmed working: 'sase bead sync-external', 'sase patch sync-external', 'sase patch set-origin'.

DEFECTS FOUND AND FIXED (epic was NOT complete):
1. Broken dead code on master. Commit eadb54323 ('Commit missing files from sase-jd.8 commit') committed 4 leftover files from sase-jd.5's ABANDONED first draft (plan external_pr_mirror.md, superseded by external_pr_mirror_1.md). src/sase/external_mirror/pull_requests.py imported ImportedPatch/import_patch/repair_patch_pr_association from sase.ace.patch.importer -- none exist -- so the module and tests/test_external_pr_mirror.py failed at import. src/sase/core/pr_mirror_facade.py called Rust bindings normalize_pull_request_url/classify_pull_request that never existed in sase-core (real names: canonical_pull_request_url/plan_external_pr_import). src/sase/doctor/checks_deep_vcs_pull_requests.py imported missing compose_chop_subprocess_env and was never registered anywhere. Independently corroborated by this bead's own third DISCOVERED ISSUE note from audit_bugs.sase.8 (mypy: 21 errors on clean master). Deleted all four after confirming zero remaining references repo-wide; the real registered doctor module checks_external_pr_mirror.py is untouched.
2. external_mirror.pr_authors never shipped. The epic plan promises it as the escape hatch narrowing 'adopt every PR'; the revised phase plan dropped it. Implemented in external_mirror/config.py (mirrored_pr_authors, factored with excluded_issue_labels) and pr_sync.py, with an 'unmirrored' MirrorReport counter, JSON schema entry, default_config.yml default, docs, and tests. Dropped records never reach the checkpoint, so clearing the knob later re-examines them.
3. PR_ORIGIN's 4th styling surface was missing (sase-jd.3 follow-up). sase-jd.3 looked in chezmoi and could not find it; the real file is syntax/sase_gp.vim in the sase-nvim LINKED REPO. Added the field label and three distinct value highlight groups matching PR_ORIGIN_VALUE_STYLES; verified with headless nvim that sase/external/unknown each resolve to their own group and the file sources without error. Committed separately in sase-nvim.

INTEGRATION: fixed 8 stale doc references the phase-8 rename missed ('PRs sub-tab', 'five top-level views ... bugs, PRs') across docs/axe.md, change_spec.md, configuration.md, getting_started.md, mentors.md, notifications.md and two blog posts; corrected the schema description that still said 'once sase-jd.5 lands'.

FOLLOW-UP OUTCOMES (all 4 child PROPOSED FOLLOW-UPs resolved or routed):
- sase-jd.3 stale symvision --epic-symbol sase-j3: already removed from the Justfile on master; tracked at sase-jg (READY). Not re-filed.
- sase-jd.3 missing PR_ORIGIN Vim syntax surface: FIXED by me in sase-nvim (see defect 3). The stale instruction path that misdirected sase-jd.3 is filed as sase-jr (READY).
- sase-jd.3 keymap registry test/config conflict: already tracked at sase-jf (READY, +1). Not re-filed.
- sase-jd.7 stale snippet_save_confirm_diff PNG golden: resolved once sase-j8 landed in the baseline.
- This bead's own 'unformatted tests/test_external_mirror_issues.py' note: fixed by c388b560c.
- DECLINED to bump the sase-core-rs floor here. core-floor-probe moved from blocked_unpublished to stale_actionable (all 5 capabilities now published: v0.24.4 for the phase-1 pair, v0.24.5 for the phase-5 pair), so the epic's blocking concern is gone and installed sase-core-rs 0.24.6 already exposes all 5. The floor DECLARATION is sase-jj's scope, which bundles the bump with regenerating uv.lock AND diagnosing why ratchet_core_window never fired -- the more valuable half. Doing half of it here would leave that bead muddled. +1 evidence with this epic's specific capabilities is already recorded on sase-jj.

VERIFICATION: 'just check' exit 0 -- every whole-repo lint gate green (fmt, ruff, mypy, keep-sorted, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation) and the scoped test lane ESCALATED TO THE FULL SUITE (rules: rename-or-delete, src-data-asset), so the entire test suite ran green. No sase-jd epic-symbol whitelist entries exist, so nothing expires at close.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-jd.1](sase-jd.1.md) | external\_ref bead identity field | ✓ closed | large | 2026-08-10 | 1 | 2 |
| [sase-jd.2](sase-jd.2.md) | Pull-request provider seam | ✓ closed | medium | 2026-08-10 | 1 | 1 |
| [sase-jd.3](sase-jd.3.md) | PR\_ORIGIN field, SASE\_PATCH stamp, and the external-Patch safety exclusion | ✓ closed | medium | 2026-08-10 | 1 | 2 |
| [sase-jd.4](sase-jd.4.md) | external\_issue\_mirror chop | ✓ closed | large | 2026-08-10 | 1 | 2 |
| [sase-jd.5](sase-jd.5.md) | external\_pr\_mirror chop and the two-file Patch importer | ✓ closed | large | 2026-08-10 | 1 | 2 |
| [sase-jd.6](sase-jd.6.md) | External-issue presentation and actions in the Beads pane | ✓ closed | large | 2026-08-10 | 1 | 1 |
| [sase-jd.7](sase-jd.7.md) | PR badge and origin chip on Patch rows and detail | ✓ closed | medium | 2026-08-10 | 1 | 2 |
| [sase-jd.8](sase-jd.8.md) | Retire Bugs, rename PRs to Patches, reorder the Artifacts sub-tabs | ✓ closed | large | 2026-08-10 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-jd: Mirror external issues into beads and external PRs into Patches [closed]"]
    n1["sase-jd.1: external_ref bead identity field [closed]"]
    n2["sase-jd.2: Pull-request provider seam [closed]"]
    n3["sase-jd.3: PR_ORIGIN field, SASE_PATCH stamp, and the external-Patch safety exclusion [closed]"]
    n4["sase-jd.4: external_issue_mirror chop [closed]"]
    n5["sase-jd.5: external_pr_mirror chop and the two-file Patch importer [closed]"]
    n6["sase-jd.6: External-issue presentation and actions in the Beads pane [closed]"]
    n7["sase-jd.7: PR badge and origin chip on Patch rows and detail [closed]"]
    n8["sase-jd.8: Retire Bugs, rename PRs to Patches, reorder the Artifacts sub-tabs [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n4
    n1 -.-> n6
    n2 -.-> n5
    n3 -.-> n5
    n3 -.-> n7
    n4 -.-> n8
    n6 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.1.md) | [sase-jd.1](sase-jd.1.md) | 2 |
| [bbugyi200.athena.sase-jd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.2/README.md) | [sase-jd.2](sase-jd.2.md) | 1 |
| [bbugyi200.athena.sase-jd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.3/README.md) | [sase-jd.3](sase-jd.3.md) | 2 |
| [bbugyi200.athena.sase-jd.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.4.md) | [sase-jd.4](sase-jd.4.md) | 2 |
| [bbugyi200.athena.sase-jd.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.5.md) | [sase-jd.5](sase-jd.5.md) | 2 |
| [bbugyi200.athena.sase-jd.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.6.md) | [sase-jd.6](sase-jd.6.md) | 1 |
| [bbugyi200.athena.sase-jd.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.7/README.md) | [sase-jd.7](sase-jd.7.md) | 2 |
| [bbugyi200.athena.sase-jd.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.8.md) | [sase-jd.8](sase-jd.8.md) | 1 |
| [bbugyi200.athena.sase-jd.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.land/README.md) | [sase-jd](README.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`498ef31`](https://github.com/sase-org/sase/commit/498ef310f611443e2a583ae1528107e99b176a69) | feat(vcs-provider): add pull-request listing seam and split issue capability probes | [sase-jd.2](sase-jd.2.md) | 2026-08-10 19:55:43 EDT |
| sase-core | [`sase-core@d0eeb48`](https://github.com/sase-org/sase-core/commit/d0eeb48324845c9d4ae946297a6b9e2d01c85c47) | feat: add Patch PR origin to core wire | [sase-jd.3](sase-jd.3.md) | 2026-08-10 20:05:45 EDT |
| sase | [`2951403`](https://github.com/sase-org/sase/commit/2951403192bb77aa7f8a9d376684f4fcf796885a) | feat: track Patch PR origin | [sase-jd.3](sase-jd.3.md) | 2026-08-10 20:07:19 EDT |
| sase-core | [`sase-core@730a78f`](https://github.com/sase-org/sase-core/commit/730a78f005b10a2b2ed99892cfed2a1111f8215f) | feat(beads): add external ref identity field | [sase-jd.1](sase-jd.1.md) | 2026-08-10 21:06:12 EDT |
| sase | [`fd93aab`](https://github.com/sase-org/sase/commit/fd93aab1d4c850d10fddb13330108d4e0627a0a1) | feat(beads): surface external refs in Python workflows | [sase-jd.1](sase-jd.1.md) | 2026-08-10 21:12:20 EDT |
| sase | [`c63b32b`](https://github.com/sase-org/sase/commit/c63b32b93c25cbbe9abc77ccf82c70b68788bb69) | feat(ace): render PR origin chip and add origin: query property | [sase-jd.7](sase-jd.7.md) | 2026-08-10 21:20:36 EDT |
| sase-core | [`sase-core@e40aa41`](https://github.com/sase-org/sase-core/commit/e40aa415e50d4e2f53da159275dc4c9516c601d0) | feat(query): add origin property to Patch query language | [sase-jd.7](sase-jd.7.md) | 2026-08-10 21:22:15 EDT |
| sase | [`1e8b373`](https://github.com/sase-org/sase/commit/1e8b373625d4f5d87921f7f171e47f0191729289) | feat(tui): surface external issues in beads | [sase-jd.6](sase-jd.6.md) | 2026-08-11 07:19:18 EDT |
| sase-core | [`sase-core@f5aa4d1`](https://github.com/sase-org/sase-core/commit/f5aa4d1d7c5b30699407192866d309cdc2f08967) | feat(external-pr): classify external pull request imports | [sase-jd.5](sase-jd.5.md) | 2026-08-11 07:29:34 EDT |
| sase | [`bdf2171`](https://github.com/sase-org/sase/commit/bdf21713a55715f5182d270201bcfa03b56c4e4a) | feat(patch): mirror external pull requests | [sase-jd.5](sase-jd.5.md) | 2026-08-11 07:30:40 EDT |
| sase-core | [`sase-core@40d0a9e`](https://github.com/sase-org/sase-core/commit/40d0a9e7ca2682e013c3208eea2659cf56066bbc) | feat(bead): collapse duplicate external\_ref issues at event-reduction time | [sase-jd.4](sase-jd.4.md) | 2026-08-11 07:38:09 EDT |
| sase | [`265fdbe`](https://github.com/sase-org/sase/commit/265fdbed82ef1638cd55bd449dd52943c33666cf) | feat(beads): mirror external tracker issues into task beads | [sase-jd.4](sase-jd.4.md) | 2026-08-11 07:51:25 EDT |
| sase | [`b5786b5`](https://github.com/sase-org/sase/commit/b5786b57f22a316af7edb5fc35789b65672d96c7) | feat(ace)!: retire the Bugs sub-tab and rename Artifacts PRs to Patches | [sase-jd.8](sase-jd.8.md) | 2026-08-11 11:36:05 EDT |
| sase | [`48617f3`](https://github.com/sase-org/sase/commit/48617f3eec9d9209ddba540ebcde5d8ff65345dd) | feat(external-mirror): add pr\_authors knob and drop abandoned PR-mirror draft | [sase-jd](README.md) | 2026-08-11 13:23:46 EDT |
| sase-nvim | [`sase-nvim@2250bbf`](https://github.com/sase-org/sase-nvim/commit/2250bbfc5a537c723809eb7d4b04ff3fb28c0ca5) | feat(syntax): highlight the PR\_ORIGIN Patch field | [sase-jd](README.md) | 2026-08-11 13:24:31 EDT |
| sase--plans | [`sase--plans@ab74aa1`](https://github.com/sase-org/sase--plans/commit/ab74aa1675423fb41d5c3c2c2fdfbae87e854006) | docs(plans): mark external artifact ingestion done | [sase-jd](README.md) | 2026-08-11 13:26:11 EDT |
