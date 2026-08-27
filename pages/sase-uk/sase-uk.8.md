# Bead: sase-uk.8 — \`v\` opens the pager

[Bead Pages](../README.md) / [sase-uk](README.md) / sase-uk.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ej](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ej.md) · **Assignee:** `sase-uk.8` · **Size:** medium
**Created:** 2026-08-26 17:44:40 EDT · **Closed:** 2026-08-27 07:43:27 EDT
**Plan:** [202608/link\_traversing\_pager.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_traversing_pager.md)

## Description

ace: route the Agents-tab `v` keymap to `SasePager` under `suspend()`, carrying the selected files as sections and the typed commit and report specs as attached targets, within the measured open-to-first-paint budget.

## Notes

[2026-08-27T11:42:47Z · sase-uk.8] PROPOSED FOLLOW-UP: the ace phase close verified functional behavior and an empirical perf sample (build_pager_document ~1ms, full open-to-first-paint via Pilot run_test ~140ms, under the 150ms budget), but did not add a dedicated bench_tui_jk.py Agents-tab case parametrized on the link_pager flag, nor a bespoke terminal-restoration test for this call site (ctrl+c/child-failure/shutdown) — that coverage is inherited from the existing generic suspend()+App.run() pattern already exercised for MemoryReviewTuiApp. A follow-up could add the explicit bench_tui_jk.py flag on/off case called out in the phase design if the shared perf budget is ever found to regress.

[2026-08-27T11:43:27Z · sase-uk.8] Replaced the bat/less shell-out in FileViewingMixin._view_files_with_pager's call site with SasePager launched under with self.suspend(), gated behind the link_pager flag (legacy method kept intact for flag-off, per design, until the land phase deletes it). Selected files build into PagerDocument sections via the existing document_from_paths adapter, off the event loop via asyncio.to_thread (tui_perf rule 1). Added SasePager.attached_handlers (new AttachedTargetHandler dispatch table consulted before resolve_ref) so CommitViewSpec hints -- which have no scannable text -- attach as AttachedTarget entries in a small 'Selected commits' manifest section and re-open CommitViewModal (or copy the sha / edit the diff path) from inside the pager; materialized tool-call/glossary/memory report files needed no such treatment since their written content already contains scannable typed refs. The pre-existing eager _open_commit_view immediate-modal behavior for commit-only selections is untouched and still fully covered by test_view_files_commits.py. Verified: full existing view-file test suites pass unchanged (tests/ace/tui/actions/, tests/pager/, 472 tests); added tests/ace/tui/actions/test_view_files_pager.py (flag on/off dispatch, off-thread document build, mixed file+commit document assembly, commit AttachedTarget copy/edit/follow dispatch) and new SasePager attached_handlers tests in tests/pager/test_app.py; just check is green (fmt, ruff, mypy, feature-flag/symvision/toobig gates, scoped test lane); empirically measured pager.open span (~37ms) and full open-to-first-paint via headless Pilot run_test (~140ms), both under the phase's 150ms budget. epic-symbols clean, no leftovers.

## Dependencies

- **Depends on:** [sase-uk.6](sase-uk.6.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-uk.9](sase-uk.9.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uk.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uk.8/README.md) | [sase-uk.8](sase-uk.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`841255d`](https://github.com/sase-org/sase/commit/841255df480a0ef7562aacc4a74c730968f103bf) | feat(ace): route the Agents-tab v keymap to SasePager under suspend() | [sase-uk.8](sase-uk.8.md) | 2026-08-27 07:44:31 EDT |
