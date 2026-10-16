# Bead: sase-1le.20.1 — Decompose the legacy root docs pages into Reference and Contribute

[Bead Pages](../README.md) / [sase-1le.20](sase-1le.20.md) / sase-1le.20.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.land`
**Created:** 2026-10-16 08:04:34 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/docs_decompose.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

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

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.land/README.md) | [sase-1le.20.1](sase-1le.20.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.7][1] | Need to determine whether the mypy failures in docs split tooling fall within this active epic | 1 |
| read-by | [agent:sase-1le.20.1.8][2] | Confirm whether the active docs-decomposition sub-epic already owns this exact mypy gate failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.8/README.md

<!-- sase:referenced-by:end -->
