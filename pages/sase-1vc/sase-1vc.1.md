# Bead: sase-1vc.1 — Key commit release evidence to the publication project

[Bead Pages](../README.md) / [sase-1vc](README.md) / sase-1vc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gj.md) · **Assignee:** `sase-1vc.1` · **Size:** medium
**Created:** 2026-11-26 07:38:27 EST · **Closed:** 2026-11-26 08:10:15 EST
**Plan:** [202611/linked\_repo\_commit\_finalization\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/linked_repo_commit_finalization_fixes.md)

## Description

release_evidence_project: resolve the commit's host project via the repo inventory, record release evidence and enqueue publication under that one key, and skip instead of failing when no project maps.

## Notes

[2026-11-26T13:10:15Z · sase-1vc.1] release_evidence_project done: commit publication now keys release evidence and the publication enqueue/hint to one host project via _resolve_commit_publication_project_key (inventory, then workspace marker, then checkpoint project_file); unmappable repos skip with a warning instead of a resumable failure; inline drain uses the same resolver against the machine store. New public wrappers: publication_project_key_for_path (agents_sync.commit_publication) and project_from_project_file (main.patch_common, renamed from private per symvision). Verified: 20/20 tests/test_commit_workflow_publication_step.py (7 new), 11/11 sibling publication modules, 95-file publication/artifact-link lane green, and sase tool run check (d9f29fe3) STATE succeeded including symvision/mypy.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vc.1/README.md) | [sase-1vc.1](sase-1vc.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`312a030`](https://github.com/sase-org/sase/commit/312a030e9f5bd0acad532ac000d18887d374dadd) | feat(commit): key release evidence to the publication project | [sase-1vc.1](sase-1vc.1.md) | 2026-11-26 08:11:49 EST |
