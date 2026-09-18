# Bead: sase-12z.4 — Switch commands, exhaustive verification, CI, and agent guidance

[Bead Pages](../README.md) / [sase-12z](README.md) / sase-12z.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mx.md) · **Assignee:** `sase-12z.4` · **Size:** medium
**Created:** 2026-09-18 10:39:54 EDT · **Closed:** 2026-09-18 17:59:18 EDT
**Plan:** [202609/fix\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots.md)

## Description

workflow-integration: expose the canonical Just recipe, call its update form from local check-full and its explicit check form from the existing CI visual job, migrate old entry points and documentation, update the two relevant reference memories, and validate the combined workflow before landing.

## Notes

[2026-09-18T19:18:03Z · sase-12z.4] PROPOSED FOLLOW-UP: SDD sidecar clone staging lacks resolvable HEAD — tests/sdd_store/test_sidecar_*.py and tests/test_linked_repo_workspaces.py::test_sidecar_materialization_uses_remote_not_divergent_primary fail independently of screenshot work; clone dest is .sase-sdd-clone-staging/.../clone instead of sase/repos/<role>.

[2026-09-18T21:59:18Z · sase-12z.4--6] Verified just fix-tui-screenshots --check (run 5e9866cfc36547e19babbe85ce531da4, monitor j71h57xsden7, exit 0) after inspecting and accepting full inventory e91e4605c16047a49d7bbbb1bacf2731. Check is clean: created=0 updated=0 unchanged=706 stale=0; pytest 967 passed (1 skipped); errors empty; pager goldens unchanged. Applied goldens: 643 ACE updates (AXE tab/footer to Services/SVC chrome plus ace.procs.default_query='-service' filter-bar seeding) and 1 stale prune of tests/ace/tui/visual/snapshots/png/axe_chop_controlled_output_120x40.png (orphan of deleted axe_chop_controlled_output). CI visual job uses --check; local check-full uses the update form. SDD sidecar clone-staging failures remain the existing PROPOSED FOLLOW-UP. Parent epic sase-12z left open for land.

## Dependencies

- **Depends on:** [sase-12z.3](sase-12z.3.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12z.4.md) | [sase-12z.4](sase-12z.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1c246dc`](https://github.com/sase-org/sase/commit/1c246dc748f687e057b7d22493b5aefc80f4dced) | feat(visual): land screenshot maintenance recipe, CI check, and refreshed goldens | [sase-12z.4](sase-12z.4.md) | 2026-09-18 18:52:38 EDT |
