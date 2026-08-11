# Bead: sase-jd.4 — external\_issue\_mirror chop

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.4` · **Size:** large
**Created:** 2026-08-10 19:14:25 EDT · **Closed:** 2026-08-11 07:37:26 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

issue_mirror: add the per-project builtin chop that diffs the tracker against beads on external_ref and creates unsized open task beads, with watermarks, a resumable backfill, per-pass budgets, backoff, a daily repair scan, a dry run, and a doctor check for detached tracker auth.

## Notes

[2026-08-11T11:37:26Z · sase-jd.4] Implemented external issue mirror per the tale: sase-core event-reducer external_ref collapse (fmt+clippy+full workspace tests green), Python external_mirror reconciliation package, sase bead sync-external CLI, external_issue_mirror AXE chop registered in checks lane with for_each projects/vcs, axe.external_mirror doctor check, config schema + docs updates. just install and just check both green except one pre-existing, unrelated flaky test (notification_store/test_mute_snooze.py, passes 3/3 isolated) which was corroborated on sase-ct/sase-h8 instead of filed as a new task.

## Dependencies

- **Depends on:** [sase-jd.1](sase-jd.1.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-jd.8](sase-jd.8.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.4.md) | [sase-jd.4](sase-jd.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@40d0a9e`](https://github.com/sase-org/sase-core/commit/40d0a9e7ca2682e013c3208eea2659cf56066bbc) | feat(bead): collapse duplicate external\_ref issues at event-reduction time | [sase-jd.4](sase-jd.4.md) | 2026-08-11 07:38:09 EDT |
| sase | [`265fdbe`](https://github.com/sase-org/sase/commit/265fdbed82ef1638cd55bd449dd52943c33666cf) | feat(beads): mirror external tracker issues into task beads | [sase-jd.4](sase-jd.4.md) | 2026-08-11 07:51:25 EDT |
