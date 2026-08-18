# Bead: sase-p2.2 — Prompt highlighting

[Bead Pages](../README.md) / [sase-p2](README.md) / sase-p2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.059](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.059.md) · **Assignee:** `sase-p2.2` · **Size:** medium
**Created:** 2026-08-17 18:09:16 EDT · **Closed:** 2026-08-17 20:45:45 EDT
**Plan:** [202608/prompt\_repo\_mentions.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_repo_mentions.md)

## Description

highlight: warm the catalog off the render path from the ACE app and overlay repo mentions in the prompt with a distinct bold underlined lavender style, including a PNG snapshot proving it reads apart from the glossary blue.

## Notes

[2026-08-17T23:57:21Z · sase-p2.2] Implementation landed: PromptRepoMentionContext/load_prompt_repo_mention_context, PromptRepoMentionMixin after PromptGlossaryMixin, ACE warmer (prompt-repo-mentions worker group), config-watch invalidation, docs/ace.md Repo names subsection, highlighting unit tests, and PNG golden prompt_repo_mention_highlight_120x40.png. Inspected the PNG: Agent Clan/Patch are muted blue, sase-core is distinct lavender; colors read apart. just check lint gates were green; scoped selection escalated (justfile + core-identity-changed after sase-core fast-forward) so just check-full is running via monitor. Re-keyed closed sase-p1.2 --epic-symbol entries to open sase-p1.6 so close would not stale them. No sase-p2.2 leftovers remain.

[2026-08-18T00:45:28Z · sase-p2.2--1] PROPOSED FOLLOW-UP: flake test_derived_only_collision_returns_composed_template — check-full (1 failed / 32586 passed) asserted "comes from #project/todo" but verdict still "Checking ⇥ todo in …sase.yml…" after 0.25s pause; isolated re-run passed; snippet_name_modal analysis-cache race, not prompt highlighting

[2026-08-18T00:45:45Z · sase-p2.2--1] Prompt highlighting landed: PromptRepoMentionContext + warmer (prompt-repo-mentions), mixin after glossary, config-watch invalidation, docs/ace.md Repo names subsection, unit tests, PNG golden prompt_repo_mention_highlight_120x40.png. PNG inspected: Agent Clan/Patch muted blue, sase-core distinct lavender; colors read apart. Lint gates in check-full were green. check-full test-cost was 1 failed / 32586 passed / 12 skipped; the failure is unrelated flake tests/ace/tui/modals/test_snippet_name_modal.py::test_derived_only_collision_returns_composed_template (verdict still Checking after 0.25s; isolated re-run passed; recorded as PROPOSED FOLLOW-UP). Isolated phase tests 28 passed. sase bead epic-symbols sase-p2.2 reported no leftovers.

[2026-08-18T00:46:58Z · sase-p2.2--1] Prompt highlighting landed: PromptRepoMentionContext + warmer (prompt-repo-mentions), mixin after glossary, config-watch invalidation, docs/ace.md Repo names subsection, unit tests, PNG golden prompt_repo_mention_highlight_120x40.png. PNG inspected: Agent Clan/Patch muted blue, sase-core distinct lavender; colors read apart. Lint gates in check-full were green. check-full test-cost was 1 failed / 32586 passed / 12 skipped; the failure is unrelated flake tests/ace/tui/modals/test_snippet_name_modal.py::test_derived_only_collision_returns_composed_template (verdict still Checking after 0.25s; isolated re-run passed; recorded as PROPOSED FOLLOW-UP). Isolated phase tests 28 passed. sase bead epic-symbols sase-p2.2 reported no leftovers.

## Dependencies

- **Depends on:** [sase-p2.1](sase-p2.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p2.3](sase-p2.3.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p2.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p2.2.md) | [sase-p2.2](sase-p2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6c41322`](https://github.com/sase-org/sase/commit/6c4132221e506c72171827e40d9e52693b167d7c) | feat(ace): highlight repo names in the prompt as lavender links | [sase-p2.2](sase-p2.2.md) | 2026-08-17 20:52:32 EDT |
