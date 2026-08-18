# Bead: sase-pw.1 — Current-project resolver over the VCS xprompt MRU

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.1` · **Size:** medium
**Created:** 2026-08-18 11:30:31 EDT · **Closed:** 2026-08-18 13:49:15 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

resolve: add `sase.current_project` with a `CurrentProject` record, an MRU-head-first resolver that maps project refs and Patch names to one enabled project, and a cheap stat-based change token for pollers.

## Notes

[2026-08-18T16:29:07Z · sase-pw.1] PROPOSED FOLLOW-UP: flake tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes — failed once in Justfile-escalated just check (assert scroll_y 0.0 == 190 on log-detail-scroll); rerun on the same tree passed. Unrelated to the current-project resolver.

[2026-08-18T17:39:33Z · sase-pw.1] PROPOSED FOLLOW-UP: ci mypy src/sase/glossary/render.py:74 — Console.color_system is str | None but Console() expects Literal[auto|standard|256|truecolor|windows] | None. Reproduces on current master without this phase tree (88fa6e949) and blocks just check before scoped tests.

[2026-08-18T17:49:15Z · sase-pw.1] Added CurrentProject, resolve_current_project, and peek_current_project_change_token in sase.current_project plus vcs_xprompt_mru_path(). Verified isolated-home tests: project-ref and Patch-name heads resolve with origin project/patch; structural #gh:owner/repo, #git:~/path, #git:home and disabled heads fall through; alias/PROJECT_NAME map to the canonical key; empty and unresolvable MRU yield None; one project-records read and one Patch-cache read per resolve; peek token is stable until record_vcs_xprompt_usage rewrites the file and degrades to the error sentinel. Re-keyed closed-palette project_accent symbols onto sase-pw.4. Escalated suite 33449 passed. just check mypy still fails on pre-existing glossary/render.py:74 (noted as PROPOSED FOLLOW-UP).

[2026-08-18T17:54:35Z · sase-pw.1] Current-project resolver lands CurrentProject, resolve_current_project, and peek_current_project_change_token; isolated-home tests cover project-ref and Patch-name heads, structural and disabled fall-through, alias/display-name resolution, empty/unresolvable None, one records read + one Patch-cache read per resolve, and peek stability/rewrite/sentinel. vcs_xprompt_mru_path() honors the _MRU_FILE hook. epic-symbols reports no leftovers; unused publics are keyed to still-open sase-pw.4.

## Dependencies

- **Blocks:** [sase-pw.4](sase-pw.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.5](sase-pw.5.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.6](sase-pw.6.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.7](sase-pw.7.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.8](sase-pw.8.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.1/README.md) | [sase-pw.1](sase-pw.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4cf7672`](https://github.com/sase-org/sase/commit/4cf7672bdf783666a3ecacaa7d72e29d6bf40a52) | feat(project): derive current project from the VCS xprompt MRU | [sase-pw.1](sase-pw.1.md) | 2026-08-18 13:55:49 EDT |
