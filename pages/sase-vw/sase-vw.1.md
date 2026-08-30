# Bead: sase-vw.1 — Link strategy frontmatter

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.1` · **Size:** medium
**Created:** 2026-08-30 10:02:15 EDT · **Closed:** 2026-08-30 10:49:21 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

schema: add `link_reference` and `link_rendering` frontmatter to flat notes, web descriptors, and strands, with strand-over-web-over-default precedence, validation, and `closure:` accepted as a legacy alias.

## Notes

[2026-08-30T14:48:28Z · sase-vw.1] PROPOSED FOLLOW-UP: init-memory AGENTS.md tests still expect Reference Memory as ### 3.1 after Memory Webs moved to the document end — they fail on unmodified HEAD where the notes render as ### 2.1 (tests/main/test_init_memory_managed_agents_descriptions.py, test_init_memory_managed_agents_frontmatter.py, test_init_memory_plan.py, test_init_onboarding_memory.py)

[2026-08-30T14:48:51Z · sase-vw.1] PROPOSED FOLLOW-UP: test_ace_and_lsp_wait_prose_replacement_ranges_match fails on unmodified HEAD — ACE wait-prose replacement end character is 30 vs LSP 8

[2026-08-30T14:49:21Z · sase-vw.1] Schema phase: link_reference/link_rendering parse on flat notes, web descriptors, and strands with strand-over-web-over-default precedence; closure: is a legacy alias (mentions->implicit, none->none) and declaring both keys is a blocker. just check lint (fmt, ruff, mypy, symvision, toobig) green. tests/memory/test_memory_web.py and tests/test_memory_notes.py 54 passed; live glossary/decisions/task_types map to implicit/none/explicit. just check test-scoped escalated (stale coverage baseline) and hit 6 pre-existing HEAD failures (AGENTS.md ### 3.1 assertions and ACE/LSP wait-prose ranges); recorded as PROPOSED FOLLOW-UP. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-vw.3](sase-vw.3.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.1/README.md) | [sase-vw.1](sase-vw.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7c8117b`](https://github.com/sase-org/sase/commit/7c8117b17e92674f99f52d98f2a44ad5481f86b8) | feat(memory): add link\_reference and link\_rendering frontmatter | [sase-vw.1](sase-vw.1.md) | 2026-08-30 10:50:34 EDT |
