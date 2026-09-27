# Bead: sase-1aq.10.7.2 — Finish the viewer acceptance matrix and dispatch landing

[Bead Pages](../README.md) / [sase-1aq.10.7](sase-1aq.10.7.md) / sase-1aq.10.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.land.md) · **Assignee:** `sase-1aq.10.7.2` · **Size:** medium
**Created:** 2026-09-26 20:01:53 EDT · **Closed:** 2026-09-26 21:17:28 EDT
**Plan:** [202609/1aq\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_remaining_acceptance.md)

## Description

viewer_matrix: finish the original live viewer and fault cases, then land the remote-dispatch bead chain.

## Notes

[2026-09-27T01:16:17Z · sase-1aq.10.7.2] viewer_matrix ade28c173a recheck done 2026-09-27T01:10Z on Apollo (no remotes configured, owner-side live matrix not runnable here): routed History/Stash overlay restores, editor apply, and reorder/add-pane all funnel through PromptInputBar._rebuild_stack->_after_rebuild, which refocuses the pane but never refreshed the %dispatch Target/Source line (fresh mounts emit no TextArea.Changed; only user typing via on_text_area_changed and _apply_dispatch_target refreshed it). A LOAD that adds/removes/changes the dispatch directive left stale target chrome: real target-selection staleness, so integrated the regression per plan. Fix: _after_rebuild now calls _refresh_dispatch_context_line() (+TYPE_CHECKING decl). Covers load_prompt_into_pane, load_stack_from_xprompt_markdown, update_active_pane. Static gates green: ruff check, ruff format --check, mypy scoped, py_compile. New pilot tests committed in tests/ace/tui/widgets/test_prompt_dispatch_context_line.py (load-shows + load-hides + focus asserts); runtime pytest NOT runnable in this workspace (sase_core_rs extension unbuilt, cold Rust exceeds turn) - recorded as follow-up for CI/land verification -r Record viewer_matrix code-level evidence

[2026-09-27T01:16:35Z · sase-1aq.10.7.2] PROPOSED FOLLOW-UP: run the two new dispatch-context pilot tests plus the full dispatch/picker lanes where sase_core_rs is built (this Apollo workspace has no compiled extension; cold maturin build exceeds single-turn limits) -r Triage runtime verification remainder

[2026-09-27T01:16:49Z · sase-1aq.10.7.2] PROPOSED FOLLOW-UP: execute the owner-side live viewer matrix on Athena with matching published builds (unfollowed-remote attention with tab/filter active, stale-gate refusal, composable project/machine queries, healthy-beside-hung host, gateway restart) with sleep-free prompts and audited pane/PNG evidence -r Triage live matrix remainder

[2026-09-27T01:17:02Z · sase-1aq.10.7.2] PROPOSED FOLLOW-UP: original owners to capture a real old locator for sase-xe.16.11.3 before exact-instance rejection, recheck its genuine healthy-beside-hung case, and close the dispatch chain in dependency order (.7.6, .7.13, .16.11.3, .16.11.5, .16.11.7, .16.11, .16.10, .16, sase-xe, sase-1aq.5/.6) with requirement-to-evidence matrices; never proxy-close -r Triage landing remainder

[2026-09-27T01:17:28Z · sase-1aq.10.7.2] viewer_matrix code scope done 2026-09-27T01:10Z: ade28c173a recheck found real dispatch-target staleness (overlay/editor restores rebuilt the stack without refreshing the Target/Source line); fixed in _after_rebuild + 2 committed pilot regressions. Verified: ruff check, ruff format --check, mypy scoped, py_compile green; epic-symbols clean; tree holds only the 2 intended files. Live owner-side matrix + chain closes left to original owners via 3 PROPOSED FOLLOW-UP notes; pilot runtime deferred to a built-extension env (recorded, not a reopen cause)

## Dependencies

- **Depends on:** [sase-1aq.10.7.1](sase-1aq.10.7.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.10.7.3](sase-1aq.10.7.3.md) ◐ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.10.7.4](sase-1aq.10.7.4.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.2/README.md) | [sase-1aq.10.7.2](sase-1aq.10.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`afca222`](https://github.com/sase-org/sase/commit/afca22227190580a79cb67e88c3b0e5c9e68cb26) | fix(ace-tui): refresh dispatch context line after prompt stack rebuild | [sase-1aq.10.7.2](sase-1aq.10.7.2.md) | 2026-09-26 21:20:52 EDT |
