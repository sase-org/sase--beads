# Bead: sase-1kh.1 — Rescue linked and external clones before any eviction

[Bead Pages](../README.md) / [sase-1kh](README.md) / sase-1kh.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.7c.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.7c.f0.md) · **Assignee:** `sase-1kh.1` · **Size:** medium
**Created:** 2026-10-13 08:22:36 EDT · **Closed:** 2026-10-13 10:50:03 EDT
**Plan:** [202610/protect\_linked\_repo\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/protect_linked_repo_work.md)

## Description

linked-rescue: rescue_git_repo every sase/repos/linked and external clone before launch eviction, re-creation, and corrupt-checkout replacement; tests and docs/workspace.md.

## Notes

[2026-10-13T14:48:55Z · sase-1kh.1] PROPOSED FOLLOW-UP: Triage two clean-base ACE hint rendering failures — ToolRun 29b7e8a6c7b8a5962449102db33c63d0 reproduced FAILED tests/ace/tui/widgets/test_agent_display_hint_cache.py::test_changed_reply_invalidates_hint_document_and_mappings and FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace from full check ToolRun 1fcd15710a7ef40f219726d90646e619; no existing bead matches either test, while the other five initially NEW failures passed on the clean base.

[2026-10-13T14:50:03Z · sase-1kh.1] Rescue helper and launch, recreation, and corrupt-checkout hooks implemented with docs and real-Git tests. just fmt and all 7 phase tests passed. sase tool run check passed lint/validation but failed 25 scoped tests; two hint tests reproduced on clean base and are recorded as a PROPOSED FOLLOW-UP. Epic symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1kh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1kh.1/README.md) | [sase-1kh.1](sase-1kh.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a638ea`](https://github.com/sase-org/sase/commit/1a638eac95b42c13014dd76c384dbfb56f5b323f) | feat(workspace): rescue linked and external clones before eviction | [sase-1kh.1](sase-1kh.1.md) | 2026-10-13 10:51:55 EDT |
