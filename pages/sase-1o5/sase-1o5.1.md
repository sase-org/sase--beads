# Bead: sase-1o5.1 — Fix the two latent shared question bugs

[Bead Pages](../README.md) / [sase-1o5](README.md) / sase-1o5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.58.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.58.linker.w0.md) · **Assignee:** `sase-1o5.1` · **Size:** small
**Created:** 2026-10-24 19:29:30 EDT · **Closed:** 2026-10-24 20:13:21 EDT
**Plan:** [202610/questions\_main\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md)

## Description

qa-bugs: stop build_merged_qa_markdown from dropping free-text answers and comments, and make option-less question rounds park for a human instead of crashing auto-resolution.

## Notes

[2026-10-25T00:13:05Z · sase-1o5.1] PROPOSED FOLLOW-UP: just check test lane has 2 clean-base failures identical with and without this phase (verified via stash): test_macro_resources_avoid_xprompt_terms (tracked by sase-1hr) and test_tui_app_import_budget 3538 vs 3537 cap (tracked by sase-1ic)

[2026-10-25T00:13:10Z · sase-1o5.1] PROPOSED FOLLOW-UP: declined-auto parked question gates carry the core decision block (outcome=auto, value=first) plus a decision-log row while journal/auto_state record manual parking; block schema cannot express declined-needs-human so no fields were invented — future provenance readers must keep relying on source/caller, never the block outcome

[2026-10-25T00:13:21Z · sase-1o5.1] qa-bugs done: _render_question now emits Answer lines for option-less free text and Comment lines for normal picks (byte-identical on all 8 legacy options shapes, proven old-vs-new); option-less auto rounds park via GateAdapter.decline_auto_execution consulted by should_auto_execute in both live and journal-resume paths. Tests: 5 new (3 qa_format, 2 gate parking incl. human free-text settlement), focused files 38 passed, sase tool run check 57459 passed with only the 2 clean-base failures already tracked by sase-1hr/sase-1ic; no epic-symbol leftovers

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1o5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.1/README.md) | [sase-1o5.1](sase-1o5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b76183e`](https://github.com/sase-org/sase/commit/b76183e9382941b325c46be867f71089b7bc8127) | fix(gates): render free-text answers and park option-less auto rounds as manual gates | [sase-1o5.1](sase-1o5.1.md) | 2026-10-24 20:14:43 EDT |
