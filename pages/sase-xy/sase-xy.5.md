# Bead: sase-xy.5 — Preserve pager link identity and resolve targets in their owning repositories

[Bead Pages](../README.md) / [sase-xy](README.md) / sase-xy.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03o--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03o.md) · **Assignee:** `sase-xy.5.land`
**Created:** 2026-09-07 13:01:40 EDT · **Closed:** 2026-09-08 02:03:05 EDT
**Plan:** [202609/pager\_target\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_integrity.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/pager_target_integrity.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_integrity.md

<!-- sase:links:end -->

## Description

Every currently rendered pager link retains a usable action and reaches the intended target when that target can be identified and accessed. Preserve typed references, source paths, URLs, commit links, and attached targets; repair the screenshot failures without suppressing links or guessing another repository.

## Notes

[2026-09-08T00:21:49Z · sase-xy.5.land] LAND AUDIT PAUSED FOR REMAINING EPIC WORK (2026-09-07): reviewed this epic and all four child records/notes, the full linked plan, current Rust/Python source, epic commits (including phase 1 scanner work co-landed inside f7852f54/e0c575503), and all post-start default-branch drift. sase-xy.4 background-resolution/context fixes, later syntax and pager line-number changes, artifact-link writer changes, pending-action reconciliation, and test bookkeeping are retained; no later pager entry point is unintegrated. Epic symbols currently report none. Remaining epic-caused gaps are captured in validated child plan sase_plan_pager_target_landing_repairs.md: clean installs still select core 0.32.34 without the new bindings; capability validation omits them; stale attached checkouts do not fall through; source_directory/project_key are unused; revisions are accepted without proof; directories escape into a Python first-hit fallback that bypasses repo scope/ambiguity/filtering; DeniedFiltered is unreachable; configured custom kinds are never passed by the pager; rich Markdown/hosted target metadata is collapsed and file fragments do not land; artifact owners attach every repository checkout and can suppress ambiguity. FOLLOW-UP OUTCOMES: sase-xy.5.1 pending_actions Symvision proposal is already resolved by the Telegram shared-API landing and host lint cleanup, so no task; sase-xy.5.2 filter-policy proposal is caused by this epic and belongs in the child plan, so no task; sase-xy.5.4 bare extensionless relative-directory proposal is additive/out of scope and became ready feature task sase-yb after duplicate/recent-task/active-epic triage found no owner. The validated child epic plan is being proposed with parent_bead sase-xy.5; resume this landing only after that child lands.

[2026-09-08T01:14:17Z · sase-xe.land--1] DISCOVERED ISSUE: c92cee70e (fix(pager): satisfy verification lint gates, authored by bbugyi200.athena.06c during this epic's master reconciliation) deleted _measure_section_heights from src/sase/pager/_layout.py but left its only caller at src/sase/pager/_layout.py:168 (height = _measure_section_heights((section,), paint_width)[0] in _paint_section_body), so mypy fails repo-wide with: src/sase/pager/_layout.py:168: error: Name "_measure_section_heights" is not defined [name-defined] — the sole mypy error across 4141 checked files. just check and just check-full therefore fail at the mypy stage on every clean tree from c92cee70e onward; confirmed at 8e00e742b (post sase-xe dispatch rebase), where the file is byte-identical to 2ba228da3 and the symbol is defined nowhere in the tree, so the dispatch landing neither caused nor touched it. Discovered 2026-09-07 during the sase-xe commit finalizer's conflict-repair verification; on that tree every other gate passed (ruff, symvision, toobig, flags, SASE validation, committed plans, and the scoped test lane, which escalated to the full suite and was green), so restoring the deleted helper or replacing the line-168 call is the only blocker to a green just check. Not filed as a task: this epic chain owns the file and its in-progress phases (sase-xy.5.5) will land pager work through the same gates.

[2026-09-08T06:03:05Z · sase-xy.5.5.4.land--1] LAND COMPLETE (2026-09-08), resuming the landing paused by note #1. All four phases (sase-xy.5.1-.4) and the remediation child epic sase-xy.5.5 are CLOSED. Note #1's paused audit listed ten epic-caused gaps and handed them to child plan plan:202609/pager_target_landing_repairs.md; every one is now closed on the combined tree and re-verified here: clean installs select released sase-core-rs 0.32.42 (== sase-core 3fa0577) with tools/validate_sase_core_rs naming the document-scan and source-target bindings and exiting 0; stale attached checkouts fall through to live same-repo inventory; source_directory/project_key drive one-component resolution; revision evidence is proven before an exact result and mismatch yields unavailable_revision; the Python first-hit directory fallback is gone and copy_text_for_target treats every owner lookup as terminal; denied_filtered is reachable from owner path_globs; configured custom kinds are frozen at every production pager entry point (re-grepped all PagerSection/PagerDocument construction sites - cli_pager, pager/resolve, pager/landings, pager/adapters, artifact_cli/read, main/pager_handler, bead/cli_show_batch, ace hints/_files); semantic target metadata including Markdown/hosted destinations and fragments survives scan->action; and document_owner_from_artifact no longer attaches unrelated repository checkouts. Note #2's blocker is resolved: _measure_section_heights has no remaining reference anywhere in src/ or tests/ and mypy is green across the repo. Note #1's three follow-up outcomes stand as recorded - the sase-xy.5.1 Symvision proposal was already resolved upstream, the sase-xy.5.2 filter-policy proposal was epic work completed in the child plan, and the sase-xy.5.4 bare-directory proposal is open ready feature task sase-yb. Post-child drift check: git fetch shows local master identical to origin/master, no unintegrated later pager entry point. sase bead epic-symbols sase-xy.5 is empty and just symvision is clean. Landing gate just check-full passed on the combined tree (exit 0; only advisory test-cost wall-clock entries).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.5.land.md) | [sase-xy.5](sase-xy.5.md) | 0 |
