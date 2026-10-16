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

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md

<!-- sase:links:end -->

## Description

Every legacy root page under docs/ lives in reference/ or contribute/ as a lookup-sized, template-shaped page. Old URLs keep working through redirects and anchor stubs, history lives only under reference/upgrading/, the legacy allowlist in docs/_meta/budgets.yml is empty, and the URL contract stays green throughout.

## Notes

[2026-10-16T14:03:20Z · sase-1le.20.1.7] DISCOVERED ISSUE: During the documentation move merge repair on 2026-10-16, required ToolRun 43e0108750a024862bdd83364e384000 failed at lint (mypy) with 9 errors in unchanged tools/render_keymap_macro_reference lines 303-306 and tools/docs_split lines 488, 674, 685, and 794. The five render_keymap errors independently reproduce the existing proposed follow-up in phase sase-1le.20.1.1 note 1; the four docs_split errors are additional in the same epic-owned tooling. Both files are byte-identical to HEAD. docs-lint and strict docs-check pass after the repair, but the full check stops before its docs and scoped-test stages.

[2026-10-16T15:18:09Z · sase-1le.20.1.8] DISCOVERED ISSUE: A separate rerun during conflict repair (ToolRun fc667fc4a5553a3af91c163a6c5d86e9) again fails at lint (mypy) with the same nine errors in tools/render_keymap_macro_reference lines 303-306 and tools/docs_split lines 488, 674, 685, and 794. The renderer's only diff is its generated-reference link path at line 349; the reported lines are unchanged, and docs_split is untouched. The strict docs build plus URL contract passes (1,420 URLs); the full check stops before later gates. This corroborates existing note #1 and adds the full-command ToolRun.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.land/README.md) | [sase-1le.20.1](sase-1le.20.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.7][1] | Need to determine whether the mypy failures in docs split tooling fall within this active epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.7/README.md

<!-- sase:referenced-by:end -->
