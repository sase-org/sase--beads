# Bead: sase-l3.3 — The grok provider module

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.3` · **Size:** medium
**Created:** 2026-08-13 14:41:47 EDT · **Closed:** 2026-08-13 17:29:07 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

provider: add `src/sase/llm_provider/grok.py` and its `sase_llm` entry point — hooks, tier/model mapping, the verified four-level effort table, the invocation vector, the interrupt/continue loop, and unit tests over recorded fixtures.

## Notes

[2026-08-13T21:28:13Z · sase-l3.3] PROPOSED FOLLOW-UP: fix prompt-panel SASE CONTEXT test cache isolation — tests/ace/tui/widgets/test_prompt_panel_header.py does not clear _memory_reads_snapshot_cache/_skill_uses_snapshot_cache, so the full-suite order can cache empty header-test context and make test_family_header_renders_followup_role_attribution fail independently of Grok provider changes.

[2026-08-13T21:29:07Z · sase-l3.3] Verified: just install completed; focused Grok provider/Messages/Grok tool-reader pytest passed (42 passed); just check passed fmt, ruff, mypy, repo audits, validation, and committed plans, then escalated to the full test lane and failed only tests/ace/tui/widgets/test_prompt_panel_header.py::test_family_header_renders_followup_role_attribution from pre-existing prompt-panel cache isolation, recorded as PROPOSED FOLLOW-UP.

[2026-08-13T21:30:17Z · sase-l3.3] Verification correction: the just check full-suite summary listed two prompt-panel header failures (test_header_renders_skill_uses_without_memory_reads and test_family_header_renders_followup_role_attribution); a direct rerun of those two nodes reproduced only the family-header failure. The recorded PROPOSED FOLLOW-UP cache-isolation issue covers the observed full-suite failures.

[2026-08-13T21:31:27Z · sase-l3.3] Implemented Grok provider and fixtures; verified just install passed, focused Grok/Messages tests passed, and just check passed lint/audits before full pytest hit unrelated prompt-panel header cache-isolation failures recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-l3.2](sase-l3.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.4](sase-l3.4.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.5](sase-l3.5.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.6](sase-l3.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.3/README.md) | [sase-l3.3](sase-l3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3085a0d`](https://github.com/sase-org/sase/commit/3085a0d287adadc52aa44a31cbd38896fe10fbc9) | feat(llm): add Grok provider | [sase-l3.3](sase-l3.3.md) | 2026-08-13 17:32:54 EDT |
