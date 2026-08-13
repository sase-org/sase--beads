# Bead: sase-kz.5 — Rewrite the prompt widget snippet mixin over the session engine

[Bead Pages](../README.md) / [sase-kz](README.md) / sase-kz.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md) · **Assignee:** `sase-kz.5` · **Size:** medium
**Created:** 2026-08-13 12:28:48 EDT · **Closed:** 2026-08-13 15:00:58 EDT
**Plan:** [plans:202608/nested\_snippet\_sessions.md](https://github.com/sase-org/sase--plans/blob/main/202608/nested_snippet_sessions.md)

## Description

widget_engine: replace the from-doc-end tabstop queue with the facade-backed session, feed every document mutation through a TextArea.edit hook, and swap the raw _snippet_tabstops reads for a session-active predicate.

## Notes

[2026-08-13T18:59:29Z · sase-kz.5] PROPOSED FOLLOW-UP: design doc deviation — the plan's "Python glue" section calls for a re-entrancy guard around edit() during the expansion's own _replace_via_keyboard call, but empirical testing showed the guard breaks the epics reported bug fix (nesting at a live outer tabstop then advancing landed mid-word instead of before the next literal text). The shipped edit() override has no guard and applies every edit (including the expansion own substitution) to the active session, which is required for outer stops to shift correctly. docs_pin phase should update the design docs Python glue section to match, and reviewers of sase-kz.6/sase-kz.7 should know the guard described there was intentionally not implemented.

[2026-08-13T19:00:11Z · sase-kz.5] PROPOSED FOLLOW-UP: just check --full scoped test lane has 32 pre-existing failures unrelated to this phase (tests/sdd/*, tests/plan_show/*, tests/test_bead/test_cli_work_from_plan*, tests/test_bead/test_design_ref_repair.py, tests/agents_sync/test_committed_plan_header.py, tests/monitor/test_monitor_supervise.py timeout tests, tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion). Verified via git stash: identical SDD/bead/plan_show failures reproduce on unmodified master, and the monitor_supervise + snippet_name_modal failures are timing-sensitive flakes that pass reliably in isolation. Worth filing as a task bead to root-cause (branch is 4 commits behind origin/master, which may be the cause for the SDD/plan ones).

[2026-08-13T19:00:58Z · sase-kz.5] Rewrote SnippetExpansionMixin over the facade-backed session (SnippetSessionState via sase_core_rs): replaced the two from-doc-end scalars with a single session object + snippet_session_active predicate, added a PromptTextArea.edit() override that feeds every edit delta to the active session, cleared the session on load_text, rewrote _expand_snippet_template_at_range/_try_advance_tabstop over plan_snippet_expansion/expand_snippet_session/advance_snippet_session, deleted the now-core-owned template-parsing helpers, and updated the 6 TYPE_CHECKING stub sites + 3 gate reads + 5 clear sites. Verified: just install rebuilt sase_core_rs and it imports; the 123 targeted tests across the 5 touched test files pass, including a new TestNestedSessions test pinning the epic's reported bug (nesting a snippet at a live outer tabstop no longer discards the outer session's remaining stops); the full tests/ace/tui/widgets/ suite (3523 tests) passes; just check's fmt/lint/symvision gates all pass (fixed 6 stale --epic-symbol Justfile entries symvision flagged as already-used); just check's scoped test lane shows 32 failures that are pre-existing/environmental -- confirmed via git stash that the same SDD/plan_show/bead-CLI failures reproduce on unmodified master, and the monitor_supervise + snippet_name_modal failures are load-timing flakes that pass in isolation. Two PROPOSED FOLLOW-UP notes recorded for the docs_pin phase (guard deviation) and for triage (pre-existing check failures).

## Dependencies

- **Depends on:** [sase-kz.4](sase-kz.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-kz.6](sase-kz.6.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-kz.7](sase-kz.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kz.5/README.md) | [sase-kz.5](sase-kz.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`16dc502`](https://github.com/sase-org/sase/commit/16dc502695d4b6025fbc4e034611ea266e38f6bf) | feat(ace): rewrite prompt snippet mixin over the facade-backed session engine | [sase-kz.5](sase-kz.5.md) | 2026-08-13 15:02:18 EDT |
