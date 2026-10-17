# Bead: sase-1le.20.1 — Decompose the legacy root docs pages into Reference and Contribute

[Bead Pages](../README.md) / [sase-1le.20](sase-1le.20.md) / sase-1le.20.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.land`
**Created:** 2026-10-16 08:04:34 EDT · **Closed:** 2026-10-16 22:25:09 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/docs_decompose.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:1770ea6d7e364bbca63ec7e4 | attached via sase artifact create --bead |
| related | file:explicit:5af1bbdc270440d8260ebb21 | attached via sase artifact create --bead |
| related | file:explicit:6243ebd33d7b5ba43264a0b8 | attached via sase artifact create --bead |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md

<!-- sase:links:end -->

## Description

Every legacy root page under docs/ lives in reference/ or contribute/ as a lookup-sized, template-shaped page. Old URLs keep working through redirects and anchor stubs, history lives only under reference/upgrading/, the legacy allowlist in docs/_meta/budgets.yml is empty, and the URL contract stays green throughout.

## Notes

[2026-10-16T14:03:20Z · sase-1le.20.1.7] DISCOVERED ISSUE: During the documentation move merge repair on 2026-10-16, required ToolRun 43e0108750a024862bdd83364e384000 failed at lint (mypy) with 9 errors in unchanged tools/render_keymap_macro_reference lines 303-306 and tools/docs_split lines 488, 674, 685, and 794. The five render_keymap errors independently reproduce the existing proposed follow-up in phase sase-1le.20.1.1 note 1; the four docs_split errors are additional in the same epic-owned tooling. Both files are byte-identical to HEAD. docs-lint and strict docs-check pass after the repair, but the full check stops before its docs and scoped-test stages.

[2026-10-16T15:18:09Z · sase-1le.20.1.8] DISCOVERED ISSUE: A separate rerun during conflict repair (ToolRun fc667fc4a5553a3af91c163a6c5d86e9) again fails at lint (mypy) with the same nine errors in tools/render_keymap_macro_reference lines 303-306 and tools/docs_split lines 488, 674, 685, and 794. The renderer's only diff is its generated-reference link path at line 349; the reported lines are unchanged, and docs_split is untouched. The strict docs build plus URL contract passes (1,420 URLs); the full check stops before later gates. This corroborates existing note #1 and adds the full-command ToolRun.

[2026-10-16T16:24:25Z · sase-1le.20.1.17] DISCOVERED ISSUE: During the paused documentation commit conflict repair on 2026-10-16, required ToolRun 6b83510d135eafea34fd8369f30c0558 failed at lint (mypy) with the same nine errors in tools/render_keymap_macro_reference and tools/docs_split already recorded in notes #1-2. Both tool files are unchanged in this repair. Explicit just docs-check passed the strict build and 1,977 URL contract checks. This is independent corroboration of the epic-owned tooling gate failure; no new task bead is warranted.

[2026-10-16T16:41:00Z · sase-1le.20.1.18] DISCOVERED ISSUE: During this docs merge conflict repair, required ToolRuns f5e04b8037aa6520244b1d91089b6f36 and aff828a1dafb486088d375604a78f3f2 both exited at lint (mypy) with the same nine errors in unchanged tools/render_keymap_macro_reference and tools/docs_split already recorded in notes 1-3. After updating the stale provider migration anchor, just docs-check passed strict build and 1,974 URL checks. just docs-lint reports unchanged docs/reference/index.md at 412 words against the 400-word hub limit (three existing contribute overruns are warnings only); the index limit belongs with the active final-hubs phase. No new task filed because the docs epic already owns both issues.

[2026-10-16T17:28:14Z · sase-1lh.1] DISCOVERED ISSUE: Gate-fix cleared these docs-epic regressions. Commit 39f9ca9300 made the generated nested deep-section pointer pass through the source-origin link rewrite; gate-fix now carries pointer metadata through anchor mapping and renders it relative to its destination page (regression asserts deep.md#deep-heading-1). Commit 5937cbc130 moved plus-one close-boundary facts into bead-cli-records.md and bead-triage.md; updated the test inputs. Commit 1c5e871e78 moved PluginsRequired batch wording to scheduler-behavior.md; updated the guard. Commit 0176c6997d moved perf_runbook.md to contribute/perf-runbook.md; updated the exact-path exception. Commits deaa5d22dd and 558e075a4d split and migrated the macro rename anchors/history; allowlisted only the moved metadata, stub, and backlink lines. The nine extensionless-tool mypy errors from prior notes were already cleared in 39f9ca9300, and the 412-word reference hub is within budget on that commit. The Deploy Docs covers:/mkdocs-exporter clash belongs to this docs epic and remains unfixed.

[2026-10-17T00:14:01Z · sase-1lh.7.land] DISCOVERED ISSUE: sase-1lh.7 lander independently found Master Gate 38983979564 at f6ff20ef2a failing docs-check for five moves.yml targets under reference/work-units/bead-cli/: sase-bead-create-1, sase-bead-dep-1, sase-bead-list-1, sase-bead-sync-1, sase-bead-task-type-1. These moved anchor IDs no longer exist after work-unit decomposition/hygiene (.9/.18); preserve historical URLs while repairing destinations. This blocks the v0.18.0 release, but is not caused by the explicit nested anchor_target fix e41b209b24. Please include this in docs landing; no duplicate task created.

[2026-10-17T00:15:01Z · sase-1lh.7.land] DISCOVERED ISSUE: A second release blocker from your .15 commit 367562ba52: src/sase/main/parser_root_help.py changed the compact memory command description to Inspect and initialize SASE memory, and audit reference memory activity, but tests/main/test_parser_root_help.py::test_root_help_renders_compact_help still asserts the old wording. Reproduced in Master Gate 38983979564 shard 7 and isolated local pytest on f6ff20ef2a. This is not caused by the later E4 parser_memory.py selector-help change. Please update the exact user-facing expectation during docs integration; no new task.

[2026-10-17T01:49:00Z · sase-1le.20.1.land] LANDER FOLLOW-UP TRIAGE (sase-1le.20.1.land, master 021f9f2316). Every PROPOSED FOLLOW-UP from phases .1-.21, plus epic notes #1-#7:
- Nine extensionless-tool mypy errors (.1#1 .3#1 .4#2 .5#1 .7#1 .8#1/#4 .9#1 .10#2/#5 .11#1 .12#2 .13#1/#5 .17#1 .18#2 .19#4; epic #1-#4). Declined: already fixed in 39f9ca9300 and the .5 recovery. typecheck_extensionless_tools is clean on 86 files.
- Generated-docs Prettier drift and the 424/412-word Reference hub (.2#1 .18#3). Declined: fixed by the gates and finish phases. just docs-lint passes.
- docs_split nested Moved-to pointers emitted root-relative (.5#2/#6, part of .13#4). Declined: fixed by c0ac5e5f56, e41b209b24, and the .13 repair.
- docs_split/docs_moves anchor model (.4#1 .5#2/#6 .13#4): duplicate headings get -N where MkDocs renders _N, underscores in code are stripped, and hyphen runs are not collapsed. EPIC-CAUSED, so it stays epic work. 99 of 1,714 pre-epic anchors no longer resolve on the built site: 97 on stubs, 2 on the prompt.md redirect. Evidence: audit script file:explicit:1770ea6d7e364bbca63ec7e4, output file:explicit:5af1bbdc270440d8260ebb21. The lander tale owns the fix.
- render_keymap_macro_reference ../../ace.md link (.5#1/#5). Declined: the renderer no longer links ace.md or macros.md.
- Canonical-plan-paths exclude and xprompt allowlist leftovers (.5#9/#14/#15 .14#1/#2 .20#2). Declined: both tests pass on master.
- init memory --check drift in home shims (.6#1 .15#1). Declined: transient drift, refreshed by f3087c86ac. The finish phase verified memory init --check.
- rust_core_backend_boundary.md still cites docs/rust_backend.md (.12#1). New memory task sase-1m0, because this epic's decisions forbid editing the core note.
- Justfile $$docs_scope makes just check always skip the docs build (.13#7). No new task: already a DISCOVERED ISSUE on causal active epic sase-1le (note #5; the sase-1le.2 gate wiring in fd8adfbe9be).
- Inherited SASE_FINALIZER_OWNED_TURN breaks conflict-repair test runs (.13#8). +1 on existing sase-19g.
- MkDocs site/ misread by pyscripts (.13#9). Declined: fixed in the .5 recovery (pyscripts skips site/, regression test).
- TUI import budget (.16#2). Declined: passes on 021f9f2316, and sase-1ic/sase-13p already track it.
- Project-label path audit (.16#2 .21#2). +1 on sase-1lx; sase-1ly duplicates it.
- Guide candidates for monitors and sudo (.19#2/#3). New feature task sase-1m1.
- Full-lane failure triage (.21#2). Declined, all already tracked: content-layout (sase-1lj; no longer red in Master Gate), completion drift sase-1de, delayed-child-bootstrap sase-12f, handoff notification sase-1io.3, supervisor SIGTERM sase-1k3. The root-help failure is epic-caused and fixed in the landing.
- Contribute pages over the 8,000-word warning cap (.21#3). New feature task sase-1m2, linked to sase-1m0.
- Epic #5, Deploy Docs. The covers: clash is gone (367562ba52/b9ac81c903). That exposed five more blockers, fixed in the lander patch file:explicit:6243ebd33d7b5ba43264a0b8: (1) mkdocs-pdf.yml '!index.md' re-included every hub index, giving a strict not-in-nav warning, now '!/index.md'; (2) mkdocs-exporter does not resolve <video poster>, fixed with a PDF-only main.html content override that points relative image posters at file://site_dir; (3) navigation.path breadcrumbs broke postprocess chapter detection, now hidden via .md-path in pdf.css; (4) validate_docs_pdf sentinels went stale after the sase-1le.19 homepage, now updated; (5) render_docs_map listed 9 draft blog posts in llms.txt, which docs-deploy-artifact-check forbids, so drafts are now skipped. Locally, just docs-lint, docs-check (3,140 URLs), docs-pdf-check (56 pages, 2.0 MiB), and docs-deploy-artifact-check all pass.
- Epic #6, five moved bead-cli anchors. Declined: fixed by b9ac81c903. docs-check passes and the Master Gate docs job is green.
- Epic #7, stale root-help expectation (caused by 367562ba52). Fixed in the lander patch.
- Integration: test_published_docs_do_not_restore_var_show still scanned the configuration.md/cli.md stubs. The lander patch retargets it to the whole docs/ tree.
- Other Master Gate reds not caused by this epic: fix_tui_screenshots help (sase-1lh.7 note records it), launch-approval/macro-group (sase-1lw), project label (sase-1lx).

[2026-10-17T02:25:09Z · sase-1le.20.1.land] Landing complete. Verified all 21 child phases are closed and reviewed every PROPOSED FOLLOW-UP. The LANDER FOLLOW-UP TRIAGE note records the disposition, new tasks sase-1m0, sase-1m1, and sase-1m2, and plus-one evidence for sase-19g and sase-1lx.

Applied the approved carry-over patch and repaired docs_moves/docs_split heading ID generation to match MkDocs, including duplicate-heading suffixes. Added the 97 missing stub aliases and both prompt-history anchors. The focused pytest set passed (33 tests). just docs-lint passed with no Reference overruns or errors; just docs-check passed with 3,284 URLs; the legacy anchor audit found 0 unresolved of 1,714; docs-pdf-check passed (56 pages, 2.0 MiB); docs-deploy-artifact-che

… and 534 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.land.md) | [sase-1le.20.1](sase-1le.20.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`08d9b66`](https://github.com/sase-org/sase/commit/08d9b66154cff1810d95a013e7567c6285c214b4) | fix(docs): match split anchors to MkDocs output | [sase-1le.20.1](sase-1le.20.1.md) | 2026-10-16 22:26:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.7][1] | Need to determine whether the mypy failures in docs split tooling fall within this active epic | 1 |
| read-by | [agent:sase-1le.20.1.8][2] | Confirm whether the active docs-decomposition sub-epic already owns this exact mypy gate failure | 1 |
| read-by | [agent:sase-1lh.1][3] | Need to report docs restructuring regressions fixed by gate-fix and avoid duplicate work | 1 |
| read-by | [agent:sase-1lh.7.5.2][4] | Need the active docs owner’s latest notes before reconciling the listed anchor and help regressions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.8/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.2/README.md

<!-- sase:referenced-by:end -->
